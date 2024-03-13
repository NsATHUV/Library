---
tags:
  - Python/内容
时间: 2023-12-27
aliases:
  - in
---
>[!info] `in` 是 Python 中的关键字，用于测试某个值是否存在于序列（如字符串、列表、元组等）中。`in` 通常用于条件语句和循环结构。

### 在条件语句中使用 `in`：

```python
value = 5
my_list = [1, 2, 3, 4, 5]

if value in my_list:
    print(f"{value} is in the list.")
else:
    print(f"{value} is not in the list.")
```

在这个例子中，`value` 是否存在于 `my_list` 中将决定 `if` 语句中哪个分支会执行。

### 在循环中使用 `in`：

```python
my_string = "Hello"

for char in my_string:
    if char in "aeiou":
        print(f"{char} is a vowel.")
    else:
        print(f"{char} is not a vowel.")
```

在这个例子中，`for` 循环用于遍历字符串中的每个字符，并通过 `if` 语句检查字符是否是元音字母。

总的来说，`in` 是用于检查成员关系的关键字，可以在条件语句和循环结构中使用，使得代码更加清晰和灵活。