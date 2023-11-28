---
tags:
  - Python/内容
---
以下是一个表格，展示了一些常见的 Python 数据类型，以及它们的示例：

| 数据类型      | 示例                        | 描述                                           |
|--------------|-----------------------------|------------------------------------------------|
| 整数（int）   | `x = 5`                     | 表示整数                                       |
| 浮点数（float）| `y = 3.14`                  | 表示实数（带有小数点）                         |
| 字符串（str） | `name = "John"`             | 表示文本数据                                   |
| 布尔值（bool）| `is_true = True`            | 表示真或假                                    |
| 列表（list）  | `numbers = [1, 2, 3]`       | 有序、可变的数据序列，可以包含不同类型的元素   |
| 元组（tuple） | `point = (10, 20)`          | 有序、不可变的数据序列                         |
| 集合（set）   | `colors = {"red", "green", "blue"}` | 无序、可变的集合，不包含重复元素       |
| 字典（dict）  | `person = {"name": "John", "age": 30}` | 无序的键值对集合                        |
| NoneType（None）| `result = None`            | 表示空值或缺失值                              |
| 复数（complex）| `z = 3 + 4j`                | 表示复数                                     |

请注意，这只是一些常见的数据类型示例。Python还有其他一些数据类型和结构，以及许多内置函数和模块，可用于更复杂的数据处理和操作。

---
### 使用 type 函数判断变量数据类型

在Python中，`type()` 函数是用于获取对象的类型的内置函数。通过传递一个对象作为参数，你可以使用 `type()` 来判断该对象的数据类型。以下是一些使用 `type()` 判断数据类型的示例：

```python
# 整数
x = 5
print(type(x))  # 输出: <class 'int'>

# 浮点数
y = 3.14
print(type(y))  # 输出: <class 'float'>

# 字符串
name = "John"
print(type(name))  # 输出: <class 'str'>

# 布尔值
is_true = True
print(type(is_true))  # 输出: <class 'bool'>

# 列表
numbers = [1, 2, 3]
print(type(numbers))  # 输出: <class 'list'>

# 元组
point = (10, 20)
print(type(point))  # 输出: <class 'tuple'>

# 集合
colors = {"red", "green", "blue"}
print(type(colors))  # 输出: <class 'set'>

# 字典
person = {"name": "John", "age": 30}
print(type(person))  # 输出: <class 'dict'>

# NoneType
result = None
print(type(result))  # 输出: <class 'NoneType'>

# 复数
z = 3 + 4j
print(type(z))  # 输出: <class 'complex'>
```

这些示例演示了如何使用 `type()` 函数来确定不同对象的数据类型。这在编写代码时很有用，特别是在处理来自用户输入或外部数据源的数据时，你可能需要确保数据的类型符合预期。

---
### 判断输入字符类型的方法

| 方法            | 描述                   | 示例                | 结果                  |
|-----------------|------------------------|---------------------|-----------------------|
| `str.isdigit()` | 是否为数字字符         | "12345".isdigit()   | True                  |
|                 |                        | "abc123".isdigit()  | False                 |
| `str.isnumeric()`| 是否为数字字符（包括    | "12345".isnumeric() | True                  |
|                 | 其他数字字符）         | "一二三四五".isnumeric() | True               |
| `str.isdecimal()`| 是否为十进制数字字符   | "12345".isdecimal() | True                  |
|                 |                        | "12.34".isdecimal()  | False                 |
| `str.isalpha()`  | 是否为字母字符         | "abc".isalpha()     | True                  |
|                 |                        | "abc123".isalpha()  | False                 |
| `str.isalnum()`  | 是否为字母或数字字符   | "abc123".isalnum()  | True                  |
|                 |                        | "!@#$".isalnum()    | False                 |
| `str.isspace()`  | 是否只包含空白字符     | "   ".isspace()     | True                  |
|                 |                        | "abc def".isspace() | False                 |
| `str.islower()`  | 是否只包含小写字母     | "abc".islower()     | True                  |
|                 |                        | "Abc".islower()     | False                 |
| `str.isupper()`  | 是否只包含大写字母     | "ABC".isupper()     | True                  |
|                 |                        | "AbC".isupper()     | False                 |
