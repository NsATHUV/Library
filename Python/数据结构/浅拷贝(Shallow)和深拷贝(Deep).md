---
tags:
  - Python/内容
aliases:
  - 浅拷贝
  - 深拷贝
日月: 2023-12-31
时分: 15:48
---
## 浅拷贝（Shallow Copy）

浅拷贝是指创建一个新的对象，该对象是原始对象的副本，但是对于原始对象中的元素，浅拷贝只复制了它们的引用而不是元素本身。换句话说，浅拷贝创建了一个新的对象，但是该对象内的元素仍然指向原始对象中相同的元素。

在Python中，可以使用不同的方式来进行浅拷贝，其中最常用的方法是使用`copy()`方法或`copy`模块中的`copy()`函数。

下面是一个示例来说明浅拷贝的概念：

```python
import copy

# 原始列表
original_list = [1, [2, 3], 4]

# 使用copy()方法进行浅拷贝
shallow_copy_list = original_list.copy()

# 使用copy模块的copy()函数进行浅拷贝
shallow_copy_list_using_module = copy.copy(original_list)

# 修改原始列表中的元素
original_list[1][0] = 'X'

# 输出原始列表和浅拷贝后的列表
print("Original List:", original_list)
print("Shallow Copy List:", shallow_copy_list)
print("Shallow Copy List Using Module:", shallow_copy_list_using_module)
```

输出结果：

```
Original List: [1, ['X', 3], 4]
Shallow Copy List: [1, ['X', 3], 4]
Shallow Copy List Using Module: [1, ['X', 3], 4]
```

在这个例子中，`original_list`是一个包含整数和子列表的列表。通过`copy()`方法和`copy`模块的`copy()`函数进行浅拷贝后，得到了两个新的列表对象，即`shallow_copy_list`和`shallow_copy_list_using_module`。虽然这两个新列表中的第一层元素是独立的，但是它们内部的子列表仍然是引用相同的对象。因此，当修改`original_list`中的子列表时，浅拷贝后的列表也会受到影响。

浅拷贝的特点是，它只复制了原始对象的表面结构，而没有递归地复制嵌套对象的内部元素。如果原始对象中包含可变对象（例如列表、字典等），则浅拷贝后的对象仍然共享这些可变对象，从而导致一些意外的行为。如果需要创建一个完全独立的对象，包括所有嵌套对象的复制，可以使用深拷贝（deep copy）。

---
## 深拷贝（Deep）

深拷贝是指创建一个新的对象，该对象是原始对象的完全独立副本，包括原始对象中的所有元素以及它们的嵌套对象。与浅拷贝不同，深拷贝不仅复制了原始对象的表面结构，还递归地复制了所有嵌套对象的内部元素，确保新创建的对象与原始对象完全独立。

在Python中，可以使用`copy`模块中的`deepcopy()`函数来执行深拷贝操作。深拷贝是通过递归地复制原始对象及其所有嵌套对象来实现的，因此即使原始对象包含了多层嵌套，深拷贝后的对象也是完全独立的，不受原始对象的影响。

以下是一个示例来说明深拷贝的概念：

```python
import copy

# 原始列表，包含嵌套的列表
original_list = [1, [2, 3], 4]

# 使用copy模块的deepcopy()函数进行深拷贝
deep_copy_list = copy.deepcopy(original_list)

# 修改原始列表中的元素
original_list[1][0] = 'X'

# 输出原始列表和深拷贝后的列表
print("Original List:", original_list)
print("Deep Copy List:", deep_copy_list)
```

输出结果：

```
Original List: [1, ['X', 3], 4]
Deep Copy List: [1, [2, 3], 4]
```

在这个例子中，通过`deepcopy()`函数进行深拷贝后，得到了一个新的列表对象`deep_copy_list`。即使修改了`original_list`中的子列表，深拷贝后的列表仍然保持不变，因为它是原始对象的完全独立副本。

深拷贝的特点是，它递归地复制了原始对象及其所有嵌套对象，确保了新创建的对象的完全独立性。这对于处理包含复杂嵌套结构的数据类型（如嵌套的列表、字典等）非常有用，因为它能够防止在修改原始对象时影响到深拷贝后的对象。