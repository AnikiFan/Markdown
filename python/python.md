# python

## 第一节课

### 成绩组成

1. 考勤
2. canvas作业
3. 课堂作业

### 内容

执行方式有解释执行和编译执行, python 是前者,这也使得它是若变量语言

python 中普通变量之间的赋值与c中类似.

在python中, 列表list[]之间的赋值类似于指针与c中的数组有很大区别.
字典{}的赋值也相当于指针之间的赋值.

和赋值所相异的动作是构造, 构造出与A一样的B的过程与指针之间的赋值不一样,
A与B是独立的, 而直接赋值是其实只是指针赋值

函数也是实参与形参相互隔离的.

对字符串作乘法即重复多少次.

`string[a:a+len]` 即string中第a+1 个字符开始的len个字符

## 第二节课

序列类型,例如字符串,列表,列表等,都支持乘法,会返回一个重复x次的种类的序列类型
加法即乘以2

只要时序列类型,就可以用下标来进行索引,从而也支持切片,同时也支持`len`和`in`

`s.count()`可以用来统计某个字符在字符串中出现的次数

`s.index()`可以返回某个字符在该字符串中的索引

```python
def chg_list(data_list)
    data_list=[]
    data_list.append(666)
    print(data_list)


def chg_list(data_list)
    data_list.append(100)
    print(data_list)
```

第一个函数不会改变所调用的列表,因为它重新构造过了,相当于把传入的指针给改变了
而第二个函数并没有重新构造,所以会改变所调用的列表

可以通过切片来替换列表中的某一部分,替换前后的部分长度可以不同

python中的元组的核心组成部分其实是逗号,圆括号是可选的.

```python
l = list("this is a string")
print(l)
```

该代码块把一个字符串拆解为一个个字符并合成一个列表

向集合中添加元素应该使用`add`方法,`remove`则用于移除元素

`dic.clear()` 与 `dic = {}` 的区别在于前者是在原地清空,而后者是重新构造了一个新的字典

## 第三节课
`None`

## 第五节课

lambda 函数可以用于行内定义新函数

```python
add = lambda x,y : x+y
print(add(1,2))
```

map 函数可以将一个函数应用于一个或多个可迭代对象的所有元素

```python 
def cube(x):
    return x**3

nums = (1,2,3,4,5)
cubes = map(cube,nums)

def to_upper(x):
    return x.upper()

person = {'name':'Alice','age':25}
names = map(to_upper,person.keys())
```

filter 函数可以根据指定的条件筛选出符合条件的元素

```python
numbers = [1,2,3,4,5]
result = list(filter(lambda x:x%2 == 0,numbers))
print(result)
```

可以用*解包列表

```python
my_list = [1,2,3,4,5]
# 将列表解包成独立的元素传递给函数
result = my_func(*my_list)
```

这等价于`result = my_func(my_list[0],my_list[1],my_list[2],my_list[3],my_list[4])`

字典则是用**来解包