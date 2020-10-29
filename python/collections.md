# collections 

该模块实现了专门的容器数据类型，给python通用内置容器数据类型（dict, list, set, tuple）提供了替代方案。

## namedtuple

创建命名tuple的工厂类，返回一个tuple类型名称的子类

    from collections import namedtuple
    User = namedtuple("User", ["name", "ID", "password", "Email"])
    u = User(name="Amy", ID="001", password="Test@123", Email="example@123")
    print(u.ID, u.name, u.password, u.Email)
    print(u[0], u[1], u[2], u[3])
    ---
    001 Amy Test@123 example@123
    Amy 001 Test@123 example@123

命名元组适合用于对于将字段名称分配给csv或sqlite3模块返回的结果。

除了从元组继承的方法外，命名元组还支持三个附加方法和两个属性。 为避免与字段名称冲突，方法和属性名称以下划线开头。

### classmethod somenamedtuple._make(iterable)

pass

### somenamedtuple._asdict()

pass

### somenamedtuple._replace(**kwargs)

pass

### somenamedtuple._fields

pass

### somenamedtuple._field_defaults

pass

要将字典转换为命名的元组，请使用双星号**

    Movie = namedtuple("Movie", "name, store")
    movie = {"name": "Mulan", "store": "1"}
    print(Movie(**movie))
    ---
    Movie(name='Mulan', store='1')


## deque

效率较高的对列表插入删除的数据类型。Deque 支持线程安全，内存高效添加(append)和弹出(pop)，从两端都可以，两个方向的大概开销都是 O(1) 复杂度。

双向队列(deque)对象支持以下方法：

append(x)
添加 x 到右端。

appendleft(x)
添加 x 到左端。

clear()
移除所有元素，使其长度为0.

copy()
创建一份浅拷贝。

count(x)
计算 deque 中元素等于 x 的个数。

extend(iterable)
扩展deque的右侧，通过添加iterable参数中的元素。

extendleft(iterable)
扩展deque的左侧，通过添加iterable参数中的元素。注意，左添加时，在结果中iterable参数中的顺序将被反过来添加。

index(x[, start[, stop]])
返回 x 在 deque 中的位置（在索引 start 之后，索引 stop 之前）。 返回第一个匹配项，如果未找到则引发 ValueError。

insert(i, x)
在位置 i 插入 x 。

如果插入会导致一个限长 deque 超出长度 maxlen 的话，就引发一个 IndexError。

pop()
移去并且返回一个元素，deque 最右侧的那一个。 如果没有元素的话，就引发一个 IndexError。

popleft()
移去并且返回一个元素，deque 最左侧的那一个。 如果没有元素的话，就引发 IndexError。

remove(value)
移除找到的第一个 value。 如果没有的话就引发 ValueError。

reverse()
将deque逆序排列。返回 None 。

rotate(n=1)
向右循环移动 n 步。 如果 n 是负数，就向左循环。

如果deque不是空的，向右循环移动一步就等价于 d.appendleft(d.pop()) ， 向左循环一步就等价于 d.append(d.popleft()) 。

## ChainMap

pass

## Counter

一个计数器工具提供快速和方便的计数。

一个 Counter 是一个 dict 的子类，用于计数可哈希对象。它是一个集合，元素像字典键(key)一样存储，它们的计数存储为值。计数可以是任何整数值，包括0和负数。

    from collections import Counter
    cnt1 = Counter([1, 2, 1, 1, 1, 1, 2, 2, 3, 3, 3])
    print(cnt1)
    print(cnt1[1])
    for num, count in cnt1.items():
        print(num, count)
    cnt2 = Counter("abcdabcdaaa")
    print(cnt2)
    c3 = Counter({'red': 4, 'blue': 2})
    print(c3)
    c4 = Counter(cats=4, dogs=8)
    print(c4)
    c5 = Counter(['eggs', 'ham'])
    print(c5)
    ------
    Counter({1: 5, 2: 3, 3: 3})
    5
    1 5
    2 3
    3 3
    Counter({'a': 5, 'b': 2, 'c': 2, 'd': 2})
    Counter({'red': 4, 'blue': 2})
    Counter({'dogs': 8, 'cats': 4})
    Counter({'eggs': 1, 'ham': 1})

## OrderedDict

pass

## defaultdict

pass

## UserDict

pass

## UserList

pass

## UserString

pass