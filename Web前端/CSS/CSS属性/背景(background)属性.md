---
tags:
  - CSS/属性
  - 内容
---
# 背景属性[^1]

| 属性                  | 描述                                       | CSS |
| ----------------------- | ---------------------------------------- | --- |
| `background`             | 复合属性。设置对象的背景特性。            | 1   |
| `background-attachment`  | 设置或检索背景图像是随对象内容滚动还是固定的。必须先指定background-image属性。 | 1   |
| `background-color`       | 设置或检索对象的背景颜色。               | 1   |
| `background-image`       | 设置或检索对象的背景图像。               | 1   |
| `background-position`    | 设置或检索对象的背景图像位置。必须先指定background-image属性。 | 1   |
| `background-repeat`       | 设置或检索对象的背景图像如何铺排填充。必须先指定background-image属性。 | 1   |
| `background-clip`         | 指定对象的背景图像向外裁剪的区域。       | 3   |
| `background-origin`     | 设置或检索对象的背景图像计算background-position时的参考原点(位置)。 | 3   |
| `background-size`         | 检索或设置对象的背景图像的尺寸大小。     | 3   |


[^1]: 详见：[菜鸟教程-CSS3背景属性](https://www.runoob.com/cssref/css-reference.html#background:~:text=3-,%E8%83%8C%E6%99%AF%E5%B1%9E%E6%80%A7,-%E5%B1%9E%E6%80%A7)

## bg-size背景图像大小[^2]

|`background-size`值|描述|
|:--|:--|
|`length`|设置背景图片高度和宽度。第一个值设置宽度，第二个值设置的高度。如果只给出一个值，第二个是设置为 `auto`(自动)|
|`percentage`|将计算相对于背景定位区域的百分比。第一个值设置宽度，第二个值设置的高度，各个值之间以空格 隔开指定高和宽，以逗号 , 隔开指定多重背景。如果只给出一个值，第二个是设置为"auto(自动)"|
|`cover`|此时会保持图像的纵横比并将图像缩放成将完全覆盖背景定位区域的最小大小。|
|`contain`|此时会保持图像的纵横比并将图像缩放成将适合背景定位区域的最大大小。|

[^2]:详见：[CSS3 background-size 属性 | 菜鸟教程 (runoob.com)](https://www.runoob.com/cssref/css3-pr-background-size.html)