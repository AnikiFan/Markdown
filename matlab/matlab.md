# matlab要点

## `table`和`array`

1. 利用`()`对`table`切片，得到的是`table`，利用`{}`对`table`切片，得到的是`array`
2. `max`等统计函数只能对`array`作用
3. 对`table`使用`dot expression`得到的是`array`
4. `()`返回的类型总是和被作用的变量类型相同，而`{}`则是更低一层的类型