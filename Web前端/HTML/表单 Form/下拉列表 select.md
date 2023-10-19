---
tags:
  - 内容
aliases:
  - select
---
#HTML标签
`<select>` 元素是HTML中用于创建下拉选择框（也称为下拉列表或下拉菜单）的表单元素。它允许用户从一组选项中选择一个或多个选项。以下是`<select>` 元素的主要特点和用法：

```html
<select name="country">
  <option value="usa">美国</option>
  <option value="canada">加拿大</option>
  <option value="uk">英国</option>
</select>
```

- `<select>` 元素是一个容器，包含一个或多个`<option>` 元素，每个`<option>` 元素代表一个可选择的选项。

- `name` 属性：用于为`<select>`元素命名，以便在提交表单时标识数据。它必须在表单内是唯一的。

- `<option>` 元素：表示选择框的各个选项，其中包括以下属性和内容：

  - `value` 属性：定义每个选项的值，该值将在表单提交时发送到服务器。这个值是可选的，如果未提供，将使用选项的文本内容作为值。
  - 文本内容：`<option>` 元素的文本内容是显示给用户的选项文本。

`<select>` 元素通常用于以下情况：

1. **单选选择框**：用户只能选择一个选项。这是默认行为。

2. **多选选择框**：用户可以选择多个选项。要使选择框支持多选，可以在`<select>`元素上使用`multiple`属性：

```html
<select name="colors" multiple>
  <option value="red">红色</option>
  <option value="green">绿色</option>
  <option value="blue">蓝色</option>
</select>
```

3. **默认选项**：您可以使用`selected`属性来指定一个或多个选项作为默认选中的选项。

```html
<select name="city">
  <option value="newyork">纽约</option>
  <option value="losangeles" selected>洛杉矶</option>
  <option value="chicago">芝加哥</option>
</select>
```

`<select>` 元素可以与其他表单元素一起使用，例如`<input>`元素和`<button>`元素，以创建更复杂的表单，以满足不同的用户输入需求。当用户提交表单时，所选选项的值将被包含在表单数据中，以便服务器端处理。这使得`<select>` 元素在创建用户友好的界面和数据收集方面非常有用。