---
tags:
  - 内容
---
#CSS/基础
# 语法
![[Web前端/Files/CSS语法.gif]]
```CSS
选择器{
	属性1:值;
	属性2:值;
	……;
	属性n:值;
}
```

示例：
```CSS
h1{
	font-size:12px;
	color:#F00;
}
```

CSS的最后一条声明后的“；”可以不写，但是基于W3C标准规范考虑，建议最后一条声明的结束“；”都要写上。

---

# 所有简单的 CSS 选择器

|选择器|例子|例子描述|
|---|---|---|
|`.class`|`.intro`|选取所有 `class="intro"` 的元素。|
|`#id`|`#firstname`|选取 `id="firstname"` 的那个元素。|
|`*`|`*`|选取所有元素。|
|element|`p`|选取所有 `<p>` 元素。|
|element,element,..|`div`, `p`|选取所有 `<div>` 元素和所有 `<p>` 元素。|