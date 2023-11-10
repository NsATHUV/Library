---
tags:
  - CSS/属性
  - 内容
---

|属性|说明|CSS|
|:--|:--|:--|
|[bottom](https://www.runoob.com/cssref/pr-pos-bottom.html)|设置定位元素下外边距边界与其包含块下边界之间的偏移|2|
|[clear](https://www.runoob.com/cssref/pr-class-clear.html)|规定元素的哪一侧不允许其他浮动元素|1|
|[clip](https://www.runoob.com/cssref/pr-pos-clip.html)|剪裁绝对定位元素|2|
|[cursor](https://www.runoob.com/cssref/pr-class-cursor.html)|规定要显示的光标的类型（形状）|2|
|[display](https://www.runoob.com/cssref/pr-class-display.html)|规定元素应该生成的框的类型|1|
|[float](https://www.runoob.com/cssref/pr-class-float.html)|规定框是否应该浮动|1|
|[left](https://www.runoob.com/cssref/pr-pos-left.html)|设置定位元素左外边距边界与其包含块左边界之间的偏移|2|
|[overflow](https://www.runoob.com/cssref/pr-pos-overflow.html)|规定当内容溢出元素框时发生的事情|2|
|[position](https://www.runoob.com/cssref/pr-class-position.html)|规定元素的定位类型|2|
|[right](https://www.runoob.com/cssref/pr-pos-right.html)|设置定位元素右外边距边界与其包含块右边界之间的偏移|2|
|[top](https://www.runoob.com/cssref/pr-pos-top.html)|设置定位元素的上外边距边界与其包含块上边界之间的偏移|2|
|[visibility](https://www.runoob.com/cssref/pr-class-visibility.html)|规定元素是否可见|2|
|[z-index](https://www.runoob.com/cssref/pr-pos-z-index.html)|设置元素的堆叠顺序|2|

# Position 属性

|值|描述|
|---|---|
|[absolute](https://www.runoob.com/css/css-positioning.html#position-absolute)|生成==绝对定位==的元素，相对于 static 定位以外的第一个父元素进行定位。<br><br>元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。|
|[fixed](https://www.runoob.com/css/css-positioning.html#position-fixed)|生成==固定定位==的元素，相对于浏览器窗口进行定位。<br><br>元素的位置通过 "left", "top", "right" 以及 "bottom" 属性进行规定。|
|[relative](https://www.runoob.com/css/css-positioning.html#position-relative)|生成==相对定位==的元素，相对于其正常位置进行定位。<br><br>因此，`left:20` 会向元素的 LEFT 位置添加 20 像素。|
|[static](https://www.runoob.com/css/css-positioning.html#position-static)|==默认值==。没有定位，元素出现在正常的流中（忽略 top, bottom, left, right 或者 z-index 声明）。|
|[sticky](https://www.runoob.com/css/css-positioning.html#position-sticky)|==粘性定位==，该定位基于用户滚动的位置。<br><br>它的行为就像 `position:relative;` 而当页面滚动超出目标区域时，它的表现就像 `position:fixed;`，它会固定在目标位置。<br><br>**注意:** Internet Explorer, Edge 15 及更早 IE 版本不支持 sticky 定位。 Safari 需要使用 -webkit- prefix (查看以下实例)。|
|inherit|规定应该从父元素继承 position 属性的值。|
|initial|设置该属性为默认值，详情查看 [CSS initial 关键字](https://www.runoob.com/cssref/css-initial.html)。|



