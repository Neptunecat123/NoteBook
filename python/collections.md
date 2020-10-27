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

pass

## ChainMap

pass

## Counter

pass

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