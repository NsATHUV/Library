---
tags:
  - 内容
  - "#CSS/属性"
aliases:
  - 字体属性
  - 文本属性
---
# 字体属性[^1]

| **属性名**    | **含义**                     | **举例**                        | **可选的值** |
| ------------- | ---------------------------- | ------------------------------- | ------------ |
| `font-family` | 设置字体类型                 | `font-family:"隶书";`           | 字体名称、字体栈 |
| `font-size`   | 设置字体大小                 | `font-size:12px;`               | 像素（px）、百分比（%）、em、rem、[[Web前端/计量单位\|等等]] |
| `font-style`  | 设置字体风格                | `font-style:italic;`            | `normal`（默认）、`italic`（使用斜体）、`oblique`（倾斜字体） |
| `font-weight` | 设置字体粗细                | `font-weight:bold;`             | 数字值（100-900）、关键词 `normal`、`bold`、`bolder`、`lighter` |
| `font`        | 在一个声明中设置所有字体属性 ==字体属性的顺序：字体风格→字体粗细→字体大小→字体类型== | `font:italic bold 36px/40px "宋体";` | `font: font-style font-weight font-size/line-height font-family` |

这些是常用的字体属性，用于控制文本的字体样式。每个属性具有特定的含义，而可选的值取决于属性的类型和用途。字体属性允许你定义文本的外观，包括字体类型、大小、风格和粗细等。

---
# 文本属性[^2]

| **属性**          | **含义**             | **举例**                           | **可选的值**                |
| ----------------- | -------------------- | ---------------------------------- | --------------------------- |
| `color`           | 设置文本颜色         | `color:#00C`                       | 颜色值、颜色名称、RGB 值等  |
| `text-align`      | 设置元素水平对齐方式 | `text-align:right;` 右对齐         | `left`、`right`、`center`、`justify` 等 |
| `text-indent`     | 设置首行文本缩进     | `text-indent:20px;` 首行缩进20像素 | 像素（px）、百分比（%）、em、rem 等 |
| `line-height`     | 设置文本行高         | `line-height:25px` 行高            | 像素（px）、百分比（%）、无单位等 |
| `text-decoration` | 设置文本的装饰       | `text-decoration:underline;` 下划线 | `none`、`underline`、`overline`、`line-through` 等 |





[^1]:详细内容见：[菜鸟教程-CSS-字体属性](https://www.runoob.com/cssref/css-reference.html#font:~:text=3-,%E5%AD%97%E4%BD%93%EF%BC%88Font%EF%BC%89%20%E5%B1%9E%E6%80%A7,-%E5%B1%9E%E6%80%A7)
[^2]:详细内容见：[菜鸟教程-CSS-文本属性](https://www.runoob.com/cssref/css-reference.html#positioning:~:text=2-,%E6%96%87%E6%9C%AC%EF%BC%88Text%EF%BC%89%20%E5%B1%9E%E6%80%A7,-%E5%B1%9E%E6%80%A7)
