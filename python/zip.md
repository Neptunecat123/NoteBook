# zip

创建一个聚合了来自每个可迭代对象中的元素的迭代器。

返回一个元组的迭代器，其中的第 i 个元组包含来自每个参数序列或可迭代对象的第 i 个元素。 当所输入可迭代对象中最短的一个被耗尽时，迭代器将停止迭代。

当只有一个可迭代对象参数时，它将返回一个单元组的迭代器。 不带参数时，它将返回一个空迭代器。

示例1：
```python
    for item in zip(["name", "age", "id"], ["zyf", "18", "001"]):
        print(item)
```
    ('name', 'zyf')
    ('age', '18')
    ('id', '001')

```python
    for item in zip(["name", "age", "id"]):
        print(item)
```
    ('name',)
    ('age',)
    ('id',)

示例2：

```python
    print(dict(zip("abc", "123")))
    print(dict(zip("abc", "1234")))
    print(tuple(zip("abcd", "123", "666")))
    print(dict(zip(["name", "age", "id"], ["zyf", "18", "001"])))
```
    {'a': '1', 'b': '2', 'c': '3'}
    {'a': '1', 'b': '2', 'c': '3'}
    (('a', '1', '6'), ('b', '2', '6'), ('c', '3', '6'))
    {'name': 'zyf', 'age': '18', 'id': '001'}