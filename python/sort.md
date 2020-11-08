# 排序指南

python列表有一个内置的list.sort()方法可以用于直接修改列表，还有一个sorted()内置函数，它会从一个可迭代对象构建一个新的排序列表。

## 基本排序

简单的升序排列，只需调用sorted()函数即可，它会返回一个新的已排序列表。

```python
sorted([5, 4, 3, 21])
----
[3, 4, 5, 21]
```

或list.sort()方法：

```python
a = [5, 4, 3, 21]
a.sort()
----
[3, 4, 5, 21]
```

区别是，list.sort()只能用于列表，sorted()函数可以接受任何可迭代对象。

## key函数

list.sort() 和 sorted() 都有一个 key 形参用来指定在进行比较前要在每个列表元素上调用的函数（或其他可调用对象）。

key 形参的值应该是个函数（或其他可调用对象），它接受一个参数并返回一个用于排序的键。 这种机制速度很快，因为对于每个输入记录只会调用一次键函数。

一种常见的模式是使用对象的一些索引作为键对复杂对象进行排序。

示例1：
```python
sorted("This is a test string from Andrew".split(), key=str.lower)
----
['a', 'Andrew', 'from', 'is', 'string', 'test', 'This']
```

示例2：
```python
student_tuples = [
    ('john', 'A', 15),
    ('jane', 'B', 12),
    ('dave', 'B', 10),
]
sorted(student_tuples, key=lambda student: student[2])   # sort by age
----
[('dave', 'B', 10), ('jane', 'B', 12), ('john', 'A', 15)]
```

## operator模块函数

上面显示的键函数模式非常常见，因此 Python 提供了便利功能，使访问器功能更容易，更快捷。 operator 模块有 itemgetter() 、 attrgetter() 和 methodcaller() 函数。

Operator 模块功能允许多级排序。 

### itemgetter() 、 attrgetter() 和 methodcaller()

to be continued

## 升序降序

list.sort() 和 sorted() 接受布尔值的 reverse 参数。这用于标记降序排序。

示例：

```python
sorted([5, 4, 3, 21], reverse=True)
----
[21, 5, 4, 3]
```

## 稳定性和复杂度

排序保证是**稳定**的。 这意味着当多个记录具有相同的键值时，将保留其原始顺序。

## [更多](https://docs.python.org/zh-cn/3/howto/sorting.html#sortinghowto)
