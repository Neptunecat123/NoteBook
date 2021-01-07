# Python语言

## 基础部分

### &sect;3.1 [核心语义](https://docs.python.org/zh-cn/3/tutorial/index.html#tutorial-index)

#### 数据结构

##### 列表

##### del语句

##### 元组/序列

##### 集合

##### 字典

##### 序列的循环

#### 模块

##### 标准模块

##### dir()函数

##### 包

#### 输入输出

#### 错误和异常

#### 类

### &sect;3.2 [标准库](https://docs.python.org/zh-cn/3/library/#metavar)

Python 标准库非常庞大，所提供的组件涉及范围十分广泛。这个库包含了多个内置模块 (以 C 编写)，Python 程序员必须依靠它们来实现系统级功能，例如文件 I/O，此外还有大量以 Python 编写的模块，提供了日常编程中许多问题的标准解决方案。

### &sect;3.2.1 [内置函数](https://docs.python.org/zh-cn/3/library/functions.html)
1. [enumerate(iterable, start=0)](python/enumerate.md)
2. [zip(*iterables)]()
3. [iter()]()

### &sect;3.2.2 [内置类型](https://docs.python.org/zh-cn/3/library/stdtypes.html)

主要内置类型有数字、序列、映射、类、实例和异常。


### &sect;3.2.3 [内置模块]()

1. [collections](python/collections.md)
2. [abc抽象基类](python/abc.md)
3. [排序指南](python/sort.md)

## 一些pythonic片段

### 1. bool判断是否有重复元素

集合的使用，判断原列表和集合后的列表是否个数相同。

```python
len(lst) == len(set(lst))
```

来源：Python程序员微信公众号 2021-01-07

### 2. bool判断组成字符串元素是否一致

判断两个字符串字符组成和个数都一致

```python
from collections import Counter
Counter(string_1) == Counter(string_2)
```

来源：Python程序员微信公众号 2021-01-07

### 3. 字符串重复打印

```python
print("abc" * 3)
```

重复打印3遍

### 4. 将2个列表组成一个字典

```python
a = ['x', 'y', 'z']
b = [1, 2, 3]

print(dict(zip(a, b)))
```

output: {'x': 1, 'y': 2, 'z': 3}

## 第三方库

1. [argparse](https://docs.python.org/zh-cn/3/howto/argparse.html)命令行解析模块
2. [requests]()
3. [Flask]()