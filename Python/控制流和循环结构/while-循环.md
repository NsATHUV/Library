---
tags:
  - Python/内容
时间: 2023-12-26
---
在Python中，`while` 循环用于在条件为真的情况下重复执行一段代码块。循环会一直执行，直到条件变为假为止。以下是 `while` 循环的基本语法：

```python
while condition:
    # Code block to be executed as long as the condition is True
    # This code block will repeat until the condition becomes False
```

在这里，`condition` 是一个表达式，当它的值为 `True` 时，循环会一直执行。当 `condition` 变为 `False` 时，循环停止，程序流程跳出循环。

如果使用break语句结束循环，可以将条件直接设置为 `True` ，循环将一直运行知道遇到 `break` 语句为止。

---
### 例子
下面是一个简单的例子，演示了一个使用 `while` 循环输出数字 0 到 4 的例子：

```python
i = 0
while i < 5:
    print(i)
    i += 1
```

在这个例子中，`i` 的初始值为 0。`while` 循环的条件是 `i < 5`，只要这个条件为真，循环会一直执行。每次循环迭代，会打印当前的 `i` 的值，然后 `i` 的值增加 1。当 `i` 的值达到 5 时，条件变为假，循环停止。

请注意，使用 `while` 循环时，需要确保循环内的代码执行过程中可以改变循环条件，以免导致无限循环。在上面的例子中，通过在循环内增加 `i += 1` 语句，确保 `i` 的值逐渐增加，最终导致循环条件变为假，从而退出循环。