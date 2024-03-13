---
tags:
  - Python/内容
aliases:
  - 双下划线方法（Double Underscore Methods）
  - 魔法方法
  - 双下划线方法
日月: 2024-01-01
时分: 10:50
---
### 表

>[!info] 提示 
>`__方法名__` 格式的方法是 Python 提供的内置方法/属性
这些特殊方法在Python中被统一地称为"魔法方法"（Magic Methods）或 "双下划线方法"（Double Underscore Methods）。它们都以双下划线 `__` 开始和结束，用于在类中实现一些特殊的行为，例如初始化、清理、字符串表示等。

| 方法名 | 类型 | 作用 |
| :--: | :--: | ---- |
| `__init__` | 方法 | 用于==初始化对象==，在对象创建时被调用。 |
| `__new__` | 方法 | 用于==创建对象==，在对象实例化之前被调用，通常不需要手动实现。 |
| `__del__` | 方法 | 用于==销毁对象==，在对象被垃圾回收时调用。 |
| `__str__` | 方法 | 返回对象的字符串表示，通过`str(obj)`或`print(obj)`调用。 |


1. `__init__`: 用于初始化对象，在对象创建时被调用。
2. `__del__`: 用于销毁对象，在对象被垃圾回收时调用。
3. `__str__`: 返回对象的字符串表示，通过`str(obj)`或`print(obj)`调用。
4. `__new__`: 用于创建对象，在对象实例化之前被调用，通常不需要手动实现。

这些方法提供了一种在类中定制对象行为的方式，使得你可以控制对象的创建、初始化、销毁以及字符串表示等方面的行为。虽然其中的一些方法在日常的类定义中并不总是必需的，但它们在需要进行特殊处理时非常有用。


---
### `__init__` 初始化

| 构造函数 | 作用 |
| --- | --- |
| `__init__(self, parameter1, parameter2, ...)` | 用于在创建类的实例时进行初始化操作，设置实例的初始属性值。该方法在对象创建时自动调用。 |
#### 参数说明：

- `self`：代表类的实例本身，用于引用实例的属性和方法。

- `parameter1, parameter2, ...`：是初始化方法的参数，用于接收在创建类实例时传递的值。

#### 示例：

考虑一个 `Car` 类的构造函数示例：

```python
class Car:
    def __init__(self, make, model, year):
        # 初始化操作，为实例设置初始值
        self.make = make
        self.model = model
        self.year = year

# 创建 Car 类的实例
car1 = Car(make="Toyota", model="Camry", year=2022)
car2 = Car(make="Honda", model="Accord", year=2021)

# 访问实例的属性
print(car1.make, car1.model, car1.year)
# 输出: Toyota Camry 2022

print(car2.make, car2.model, car2.year)
# 输出: Honda Accord 2021
```

在这个例子中，`__init__` 方法用于初始化 `Car` 类的实例属性 `make`、`model` 和 `year`。在创建类的实例时，通过传递相应的参数来为这些属性设置初始值。

---
### `__new__` 创建对象

| 方法 | 作用 |
| --- | --- |
| `__new__(cls, *args, **kwargs)` | 用于创建一个新的实例对象。在实例创建之前调用，负责对象的创建和返回。 |
#### 参数说明：

- `cls`：代表类本身，即将要实例化的类。
  
- `*args`：表示位置参数，用于接收传递给 `__new__` 方法的非关键字参数。

- `**kwargs`：表示关键字参数，用于接收传递给 `__new__` 方法的关键字参数。

#### 返回值：

- 必须返回一个新的实例对象。

#### 示例：

考虑一个简单的 `Singleton` 单例模式的 `__new__` 方法示例：

```python
class Singleton:
    _instance = None

    def __new__(cls, *args, **kwargs):
        # 如果实例不存在，则创建一个新的实例；否则，返回已有的实例
        if not cls._instance:
            cls._instance = super().__new__(cls, *args, **kwargs)
        return cls._instance

# 创建 Singleton 类的实例
singleton1 = Singleton()
singleton2 = Singleton()

# 判断两个实例是否相同
print(singleton1 is singleton2)
# 输出: True
```

在这个例子中，`__new__` 方法用于实现单例模式，确保只创建一个实例。如果实例不存在，则创建一个新的实例；否则，返回已有的实例。

---
### `__del__` 销毁

| 方法 | 作用 |
| --- | --- |
| `__del__(self)` | 用于在对象被销毁时执行一些清理工作。在对象的引用计数为零时，即没有任何引用指向该对象时被调用。 |
#### 参数说明：

- `self`：代表类的实例本身，用于引用实例的属性和方法。

#### 注意事项：

- 不建议过度依赖 `__del__` 方法，因为它的执行时机不确定，不同的 Python 实现可能有不同的行为。

- 一般情况下，推荐使用 `with` 语句、`try`/`except` 语句等来进行资源的管理和清理，而不是依赖 `__del__`。

#### 示例：

考虑一个简单的 `Person` 类的 `__del__` 方法示例：

```python
class Person:
    def __init__(self, name):
        self.name = name

    def __del__(self):
        print(f"{self.name}对象被销毁")

# 创建 Person 类的实例
person = Person(name="Alice")

# 删除引用，触发 __del__ 方法
del person
# 输出: Alice对象被销毁
```

在这个例子中，`__del__` 方法用于在对象被销毁时打印一条消息。当删除对 `Person` 实例的最后一个引用时，`__del__` 方法被调用。

---
### `__str__` 返回对象描述

| 方法 | 作用 |
| --- | --- |
| `__str__(self)` | 用于返回对象的用户友好字符串表示。当使用内置函数 `str()` 或 `print()` 函数时被调用。 |
#### 参数说明：

- `self`：代表类的实例本身，用于引用实例的属性和方法。

#### 返回值：

- 必须返回一个字符串，表示对象的用户友好字符串表示。

#### 示例：

考虑一个简单的 `Book` 类的 `__str__` 方法示例：

```python
class Book:
    def __init__(self, title, author):
        self.title = title
        self.author = author

    def __str__(self):
        return f"Book: {self.title} by {self.author}"

# 创建 Book 类的实例
book = Book(title="The Great Gatsby", author="F. Scott Fitzgerald")

# 使用 str() 函数和 print() 函数触发 __str__ 方法
print(str(book))
# 输出: Book: The Great Gatsby by F. Scott Fitzgerald
```

在这个例子中，`__str__` 方法用于返回 `Book` 类实例的用户友好字符串表示。当使用 `str()` 函数或 `print()` 函数时，会触发 `__str__` 方法。