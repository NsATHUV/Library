---
tags:
  - Python/内容
时间: 2023-12-25
aliases:
  - 变量
---
### 1. 什么是变量？

变量是用于存储和表示数据值的标识符。在编程中，我们使用变量来命名和存储数据，使得我们可以在程序中引用和操作这些数据。

---
### 2. 变量的命名规则

- 变量名由字母（大小写均可）、数字和下划线组成。
- 变量名不能以数字开头。
- Python中的变量名区分大小写。
- 避免使用Python关键字作为变量名。
#### 展开讲解
在 Python 中使用变量时，需要遵守一些规则和指南。违反将引发错误，而指南旨在让编写的代码更容易阅读和理解。规则如下：
- 变量名只能包含字母、数字和下划线[^1]。变量名能以字母或下划线开头，不能以数字开头。例如，`message_1`可以，但`1_message`不行。
- 变量名不能包含空格，但能使用下划线来分隔其中的单词。例如，变量名`greeting_message`可行，但变量名`greeting message`会引发错误。
- 不能使用 Python 关键字和函数名作为变量名。例如，`print`不能单独作为变量名，但可以加下划线和数字来区别后使用。
- 变量名应及尖端又具有描述性。例如，`name `比`n`好，`student_name`比`s_n`好，`name_length`比`length_of_persons_name`好。不必因为缩写更方便，而使用不易读的变量名，因为不论是[[Python/Python & 编程环境#代码编辑器和IDE|IDE还是代码编辑器]]，都可以让你快速输入已声明的变量。
- 慎用小写字母`l`和大写字母`O`，因为可能被误读为`1`或`0`。

> [!warning] **注意**：应使用小写的 Python 变量名。虽然在变量名中使用大写字母不会导致错误，但大写字母通常被用来声明常量，如元组。

---
### 3. 变量声明

和其他编程语言类似，但[[Python/变量和数据类型/Python-数据类型#数据类型|数据类型]]不是必须声明的。
```python
变量名 = 值
```
#### Python 特有的声明变量语法

```python
变量名1,变量名2,……,变量名n = 值1,值2,……,值n
```

---
### 4. Python 关键字

```python
False      await      else       import     pass
None       break      except     in         raise
True       class      finally    is         return
and        continue   for        lambda     try
as         def        from       nonlocal   while
assert     del        global     not        with
async      elif       if         or         yield
```