---
tags:
  - CSS/属性
  - 内容
---
# 边框属性[^1]

| 属性                   | 说明                                                                         | 示例                                 |
| ---------------------- | ---------------------------------------------------------------------------- | ------------------------------------ |
| `border-top-color`     | 上边框颜色                                                                   | `border-top-color:#369;`             |
| `border-right-color`   | 右边框颜色                                                                   | `border-right-color:#369;`           |
| `border-bottom-color ` | 下边框颜色                                                                   | `border-bottom-color:#fae45b;`       |
| `border-left-color `   | 左边框颜色                                                                   | `border-left-color:#efcd56; `        |
| `border-color`         | 四个边框为同一颜色                                                           | `border-color:#eeff34; `             |
|                        | 上、下边框颜色：#369`<br><br>`左、右边框颜色：`#000`                         | `border-color:#369 #000;`            |
|                        | 上边框颜色：#369`<br><br>`左、右边框颜色：`#000``<br><br>`下边框颜色：`#f00` | `border-color:#369 #000 #f00;`       |
|                        | 上、右、下、左边框颜色：`<br><br>``#369`、`#000`、`#f00`、`#00f `            | `border-color:#369 #000 #f00 #00f; ` |
| `border`               | 复合属性                                                                     | `border:1px red solid`                                     |

### border 复合属性
可以使用下面列出的一个，两个或三个值来指定 border 属性，==值的顺序无关紧要==：
```CSS
/* 边框样式 */
border: solid;

/* 边框宽度 | 边框样式 */
border: 2px dotted;

/* 边框样式 | 边框颜色 */
border: outset #f33;

/* 边框宽度 | 边框样式 | 边框颜色 */
border: medium dashed green;

/* 全局值 */
border: inherit;
border: initial;
border: unset;
```

#### 注意
以上示例不仅代表`border`，也可以用于其他方向上的，例如`border-top`、`borer-bottom`。



[^1]:详见-[菜鸟教程-边框属性](https://www.runoob.com/cssref/css-reference.html#flexbox:~:text=%E8%BE%B9%E6%A1%86(Border)%20%E5%92%8C%20%E8%BD%AE%E5%BB%93(Outline)%20%E5%B1%9E%E6%80%A7)