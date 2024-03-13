---
tags:
  - Python/内容
时间: 2023-12-26
---
>[!info] for循环
>`for`循环通常有两个作用：
>1. 一个是执行特定次数的循环
>2. 另一个则是遍历可迭代对象（列表，元组，字典，字符串等）。

---
### 1. 执行特定次数的循环

可以使用 `for` 与 [[Python/控制流和循环结构/for-循环#`range()` 函数生成整数序列|range()]] 来做到控制循环次数，相比使用 [[Python/控制流和循环结构/while-循环|while-循环]] 并设置控制循环次数的变量，使用 `for` 更简洁。

```python
for i in range(次数):
	# 代码块
```
- `i` : 是一个局部变量，取什么名字无所谓，甚至可以是 `_` ，当第一次执行循环时，为 `range()` 生成的第一个数字，以此类推。
- `in`：即 [[Python/控制流和循环结构/in-关键字|in]] 关键字。
- `代码块`：在执行代码中，`i` 可以被调用，也可以不调用。

---

### 2. 使用 `for循环` 遍历可迭代元素

>[!warning] 本质上，[[Python/控制流和循环结构/for-循环#1. 执行特定次数的循环|第一种]]用法和当前所讲用法是同同一类用法，同样是遍历一个可迭代对象，`range()`函数的结果是生成一个数字序列，类型为 `range`。

当使用 `for` 循环遍历可迭代对象时，我们能够便捷地访问对象中的每个元素。可迭代对象包括列表（list）、元组（tuple）、字符串（string）、字典（dictionary）、集合（set）等。下面是关于使用 `for` 循环遍历可迭代对象的一些要点：
#### 1. 遍历列表：

```python
my_list = [1, 2, 3, 4, 5]

for item in my_list:
    print(item)
```

在这个例子中，`for` 循环迭代 `my_list` 中的每个元素，将元素赋值给变量 `item`，然后执行循环体内的代码块。
#### 2. 遍历元组：

```python
my_tuple = (10, 20, 30, 40, 50)

for item in my_tuple:
    print(item)
```

同样，`for` 循环也适用于遍历元组，每个元素都会按顺序赋值给变量 `item`。
#### 3. 遍历字符串：

```python
my_string = "Hello"

for char in my_string:
    print(char)
```

对于字符串，`for` 循环将逐个遍历每个字符，并执行相应的代码块。
#### 4. 遍历其他可迭代对象：

```python
my_set = {1, 2, 3, 4, 5}

for element in my_set:
    print(element)
```

可迭代对象不仅限于列表、元组和字符串，还包括集合等其他数据结构。

---

### `range()` 函数生成整数序列
在 Python 中，`range()` 是一个用于生成整数序列的内置函数。其基本语法如下：

```python
range(stop)
range(start, stop)
range(start, stop, step)
```

- `start`: 序列的起始值（可选，默认为0）。
- `stop`: 序列的终止值，不包括该值。
- `step`: 步长，表示每个数之间的间隔（可选，默认为1）。

`range()` 返回一个可迭代对象，通常与 `for` 循环一起使用。以下是一些示例：

1. **只提供 `stop` 参数：**

   ```python
   for i in range(5):
       print(i)
   ```
   输出：
   ```
   0
   1
   2
   3
   4
   ```

2. **提供 `start` 和 `stop` 参数：**

   ```python
   for i in range(2, 8):
       print(i)
   ```
   输出：
   ```
   2
   3
   4
   5
   6
   7
   ```

3. **提供 `start`、 `stop` 和 `step` 参数：**

   ```python
   for i in range(1, 10, 2):
       print(i)
   ```
   输出：
   ```
   1
   3
   5
   7
   9
   ```

请注意，`range()` 生成的序列是==左闭右开==区间，即包括 `start` 值，但不包括 `stop` 值。`step` 参数表示序列中相邻两个值的间隔，默认为1。

还可以使用 `list()` 函数将 `range()` 的输出转换为列表，例如：

```python
my_list = list(range(3, 10, 2))
print(my_list)
```
输出：
```
[3, 5, 7, 9]
```

