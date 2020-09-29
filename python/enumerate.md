# enumerate(iterable, start=0)

返回一个枚举对象。iterable必须是一个序列，或iterator，或其他支持迭代的对象。enumerate()返回的迭代器的`__next__()`方法返回一个元组，里面包含一个计数值（从start开始，默认start为0）和通过迭代iterable获得的值。

    weekday = ['mon', 'tue', 'wed', 'thur', 'fri', 'sat', 'sun']
    print(list(enumerate(weekday)))
    print(list(enumerate(weekday, start=10)))
    ---
    [(0, 'mon'), (1, 'tue'), (2, 'wed'), (3, 'thur'), (4, 'fri'), (5, 'sat'), (6, 'sun')]
    [(10, 'mon'), (11, 'tue'), (12, 'wed'), (13, 'thur'), (14, 'fri'), (15, 'sat'), (16, 'sun')]

等价于

    def enumerate1(sequence, start=0):
        n = start
        for elem in sequence:
            yield n, elem
            n += 1

    print(list(enumerate1(weekday, start=100)))
    ---
    [(100, 'mon'), (101, 'tue'), (102, 'wed'), (103, 'thur'), (104, 'fri'), (105, 'sat'), (106, 'sun')]