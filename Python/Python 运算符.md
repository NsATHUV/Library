---
tags:
  - Python/内容
时间: 2023-11-27
aliases:
  - 运算符
---
### 算术运算符

| 运算符 | 含义 | 示例 | 结果 |
| ---- | ---- | ---- | ---- |
| `+` | 加法 | `3 + 5` | `8` |
| `-` | 减法 | `7 - 2` | `5` |
| `*` | 乘法 | `4 * 6` | `24` |
| `/` | 除法 | `9 / 3` | `3.0` |
| `%` | 取模（取余数） | `10 % 4` | `2` |
| `**` | 幂运算 | `2 ** 3` | `8` |
| `//` | 整除（取商的整数部分） | `11 // 3` | `3` |

---
### 比较运算符

| 运算符 | 含义 | 示例 | 结果 |
| ---- | ---- | ---- | ---- |
| `==` | 等于 | `x == y` | `True` 或 `False`（取决于 x 和 y 的值） |
| `!=` | 不等于 | `a != b` | `True` 或 `False`（取决于 a 和 b 的值） |
| `<` | 小于 | `5 < 8` | `True` |
| `>` | 大于 | `7 > 4` | `True` |
| `<=` | 小于等于 | `6 <= 6` | `True` |
| `>=` | 大于等于 | `9 >= 10` | `False` |
### 逻辑运算符

| 运算符 | 含义 | 示例 | 结果 |
| ---- | ---- | ---- | ---- |
| `and` | 与 | `True and False` | `False` |
| `or` | 或 | `True or False` | `True` |
| `not` | 非 | `not True` | `False` |

---
### 赋值运算符

| 运算符 | 含义 | 示例 | 结果 | 三目运算符 | if-else语句 |
| ---- | ---- | ---- | ---- | ---- | ---- |
| `=` | 简单赋值 | `x = 10` | `x` 的值为 `10` | `result = x if condition else y` | `if condition: result = x else: result = y` |
| `+=` | 加法赋值 | `a += 3` | `a` 的值增加 `3` | `result = a + 3 if condition else a` | `if condition: a += 3` |
| `-=` | 减法赋值 | `b -= 2` | `b` 的值减少 `2` | `result = b - 2 if condition else b` | `if condition: b -= 2` |
| `*=` | 乘法赋值 | `c *= 4` | `c` 的值乘以 `4` | `result = c * 4 if condition else c` | `if condition: c *= 4` |
| `/=` | 除法赋值 | `d /= 5` | `d` 的值除以 `5` | `result = d / 5 if condition else d` | `if condition: d /= 5` |
| `%=` | 取模赋值 | `e %= 3` | `e` 的值取模 `3` | `result = e % 3 if condition else e` | `if condition: e %= 3` |
| `**=` | 幂运算赋值 | `f **= 2` | `f` 的值平方 | `result = f ** 2 if condition else f` | `if condition: f **= 2` |
| `//=` | 整除赋值 | `g //= 3` | `g` 的值整除 `3` | `result = g // 3 if condition else g` | `if condition: g //= 3` |

> [!warning] 注意
> [[C语言笔记/运算符/算数运算符#目的概念|三目]]运算符（**条件表达式**）在 Python 中的语法为 `x if condition else y`，它表示如果条件为真，则结果为 `x`，否则结果为 `y`。在适当的位置插入三目运算符和条件语句时，请根据具体情况选择。

---
### 位运算符

| 运算符 | 含义 | 示例 | 结果 | 三目运算符 | if-else语句 |
| ---- | :--: | ---- | ---- | ---- | ---- |
| `&` | 按位与 | `4 & 5` | `4` | `result = 4 & 5 if condition else 0` | `if condition: result = 4 & 5 else: result = 0` |
| `\|` | 按位或 | `4 \| 5` | `5` | `result = 4 \| 5 if condition else 0` | `if condition: result = 4 \| 5 else: result = 0` |
| `^` | 按位异或 | `4 ^ 5` | `1` | `result = 4 ^ 5 if condition else 0` | `if condition: result = 4 ^ 5 else: result = 0` |
| `~` | 按位取反 | `~4` | `-5` | `result = ~4 if condition else 0` | `if condition: result = ~4 else: result = 0` |
| `<<` | 左移 | `4 << 2` | `16` | `result = 4 << 2 if condition else 0` | `if condition: result = 4 << 2 else: result = 0` |
| `>>` | 右移 | `8 >> 2` | `2` | `result = 8 >> 2 if condition else 0` | `if condition: result = 8 >> 2 else: result = 0` |

>[!success] 第二行的内容中，`|`前面的`\`无需在意，这是转义符号。

> [!warning] 注意
> [[C语言笔记/运算符/算数运算符#目的概念|三目]]运算符（**条件表达式**）在 Python 中的语法为 `x if condition else y`，它表示如果条件为真，则结果为 `x`，否则结果为 `y`。在适当的位置插入三目运算符和条件语句时，请根据具体情况选择。
