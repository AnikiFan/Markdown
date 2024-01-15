# CS61A

## python使用技巧、

1. `python -i test.py`能以交互模式启动文件
2. `python -m doctest test.py`能自动测试`docstring`中所写的样例，格式为`>>> clause`，下一句为期望输出，写在`docstring`中

## 编程思想

1. 抽象数据类型，通常有多层抽象，每一层只能使用下一层的抽象，不能使用更底层的抽象
   1. 最底层的基础类型，例如`list`，整型
   2. 自定义类型以及构造函数和对外接口，例如有理数类，以及获得分子分母的接口
   3. 高阶操作接口，例如打印有理数，有理数运算
   4. 实际应用，例如在编写计算器程序时使用有理数类

## python语法基础

1. 函数调用即`operator ( operand 1 , operand 2 , ...)`，执行时先依次求`operator,operand1,operand2,...`的值，然后执行`operator`
2. `a,b,c,..=exp1,exp2,exp3,...`的执行过程是先对`exp1`,`exp2`,`exp3`等表达式求值，然后依次赋值
3. `python`中的赋值语句理解为等号右侧为*值*，而非*变量*，所以即使所赋的值之后有变动，被赋的值不会随之改变，这与`C`中的指针不同
4. `python`中用`and,or`联结的条件语句遵循短路逻辑，返回值是最后一个求值的表达式，不一定是布尔值，例如`True and "test"`的返回值是`'test`，在需要布尔值的地方才会进一步将他们转换为布尔值
5. 可以在一句内使用条件语句`条件成立时执行语句 if 条件 else 条件失败时执行语句`，这也可以作为一个表达式嵌入其他语句中
6. `lambda`语句可以定义一个匿名函数，例如`lambda x:x*x`，`lambda`后跟的是形参表,`:`后跟的是返回值。`lambda`的常见用途是定义后直接赋值给其他变量或实参，供后续使用
7. `assert`语句可以用于处理错误输入，格式为`assert statement1,prompt`当`statement1`为假时，程序会退出，`prompt`会显示在提示中
8. 函数当返回字符串时，都是用单引号`''`，尽管双引号也是合法的
9. 高阶函数，即形参或返回值中有函数的函数。我们可以在一个函数体中使用`def`语句来创建新函数
10. `python`中的变量生命周期的概念与`C`不相同，但和`R`语言中的环境概念相同，在查找一个变量名时，会不断向上一个环境追溯，知道找到该变量名对应的值

``` python
def father(x):
    '''
    >>> fun = father(1) # fun的值为son函数，其父环境是father函数，其父环境是Global
    >>> fun(2) # 调用son函数，其中的x变量在其父环境——father函数中找到；理解为son函数中的x已经被替换为了1是不准确的，实际上有个向上查找的过程
    3 
    '''
    def son(y):
        return y+x*x
    return son
```

11. 一个函数的父环境取决于它的`def`语句所处环境，本质上`def`语句会在该环境中创建一个对象，函数名只是指向该对象的一个只读指针
12. 将一个多参数函数拆分为多个单参数高阶函数的技巧称为`currying`

```python
def test(x,y):
    return x+y

currying = lambda func : lambda x : lambda y : func(x,y)

currying_test = currying(test)

"""
>>> test(2,4)==currying_test(2)(4)
True
"""
```

13. `decorator`装饰器，即一类形参表为1个函数，并返回一个函数的高阶函数。使用时，在`@decorator`后使用`def`语句定义函数`fun`，则在调用`fun`时，实际上调用的是`decorator(fun)`

```python
def decorator(fun):
    def decorated(a,b):
        result = fun(a,b)
        print("return ",result)
        return 
    return decorated

@decorator
def test(a,b):
    """
    >>> test(1,3)
    return 4
    """
    return a+b
```

14. `unpacking`:n元`list`可以直接赋值给n个变量，无需使用`[]`运算符
15. *Slicing Create New Values*
16. `is`用于判断`Identity`，而`==`用于判断`Equality`，前者更严格，要求是同一对象，而后者允许值相同的不同对象
17. ***A default argument value is part of a function value, not generated by a call***

```python
def f(s=[])
    s.append(5)
    return len(s)
"""
>>> f()
1
>>> f()
2
>>> f()
3
"""
```

18. `list`和函数一样是对象，变量名只是指向该对象，在调用形参为列表名的函数时，要注意调用函数的规则，是先求值后运算，所以实际上传进去的是对象本身，而非新的列表
19. 使用一个变量名时，会沿着父环境查找该变量名。当给一个变量名赋值时，若当前环境中没有变量名，则在当前环境中创建该变量。使用`nonlocal`在当前环境中声明该变量名，则给该变量名赋值时，也会沿父环境查找该变量名。使用`nonlocal`声明的前提是当前环境中没有该变量名，且沿父环境能够查找到该变量名，否则会报错
20. `mutable function`，即含有可变的参数的函数。一般利用高阶函数实现。因为如果使用一阶函数的话，如果可变参数在函数体内初始化，那么每一次调用该函数时都会初始化一次。当然也可以把可变参数放在`Global`中，但是这会导致误操作的风险

```python
def make_withdraw(total):
    """每次调用时会产生一个环境，其中有total和对应的withdraw函数"""
    def withdraw(money): #能够记忆total的变化情况，
        nonlocal total
        total-=money
        print(total)
    return withdraw
"""
>>> me = make_withdraw(100)
>>> me(50)
50
>>> another_account = me
>>> another_account(30)
20
>>> he = make_withdraw(200)
>>> he(50)
150
>>> me(0)
20
"""
```

21. 函数和list在python中都可以理解为存储在环境中的对象，变量名是refer到他们，而非存储他们，refer他们的变量名赋值给其他变量时，是让其他变量refer到同一对象，而非让对方存储的值变为自身
22. 可以使用`iter`函数生成可遍历对象的遍历器，例如`list`,`tuple`。使用`next(iter)`可以返回遍历器当前所指元素，并将其移向下一个位置。当遍历器遍历完所有元素后，如果在此调用`next`则会报错。可以直接利用`list`,`tuple`,`sorted`等函数作用在遍历器中以生成新的容器，所得到容器只包含为遍历的元素，且会把遍历器移到尾部。遍历器也可以用于`for`循环，这和使用`next`一致。
23. 很多和遍历有关的内置函数都是`lazy function`，也就是只有在需要的时候才会进行求值。例如`map(func,iterable)`,`filter(func,iterable)`,`zip(first_iter,second_iter)`,`reversed(sequence)`这些函数都会返回有关特定元素的遍历器。
    - `map(func,iterable)`遍历每个元素，将其作用在`func`中，并返回其返回值
    - `filter(func,iterable)`遍历每个元素，将其作用在`func`中，当`func`返回`True`时，返回该元素
24. 迭代器在使用的过程中，被迭代对象的大小不能发生变化，但是值可以发生变化
25. 当一个函数没有`return`语句，而是有一个或多个`yield`语句时，该函数是一个生成器，作用和遍历器一样，使用`next`来获取下一个`yield`的值，并且遵循`lazy function`
26. 在生成器函数中，可以使用`yield from`直接从可循环对象中生成`yield`的值，省略了遍历的过程
27. `python`中的一个类有3个组成部分`method`,类公有的`attribute`和每个成员私有的`attribute`。在`__init__(self)`函数中定义的有`self.`前缀的变量便是私有的`attribute`。在`python`中，`class.fun(self,...)`是`function`，此时`self`参数需要人为填入，而`object.fun(self)`才是`method`，此时`self`参数会自动填入`object`

```python
class test:
    x = "this is a public attr"
    def func(self):
        return 0

    def __init__(self):
        self.y = "this is a private attr"
```

28. `expression.name`的求解过程为：先求`expresstion`，然后在得出来的对象中寻找`name`，找到则返回该属性，否则在该对象对应的类中寻找公共属性
29. 可以直接使用`expression.name`表达式来为对象创建一个新的属性，如果该属性与该对象对应的类中的公共属性重名，那么也是允许的，且使用同一`expression.name`所得到的值不会因为公共属性的改变而改变，这是由于属性查找规则决定的
30. 使用继承时，并不是自动将父类复制一份，而是构建了一条查找链，例如构造子对象时`__init__()`函数实际上就是向上查找，在父类中找到，所以调用了父类的`__init__()`函数，如果子类有自己的`__init__()`函数，则会覆盖掉父类的`__init__()`函数