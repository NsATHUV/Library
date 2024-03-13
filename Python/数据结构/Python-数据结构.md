---
tags:
  - Python/简介
aliases: 
日月: 2023-12-31
时分: 21:44
---
### 简介

>[!info] 数据结构
>
>Python 提供了丰富的内置数据结构，用于组织和存储数据。以下是一些常见的 Python 数据结构：
>
>1. **列表（List）:**
>   - 用于存储有序的元素集合。
>   - 可以包含不同类型的元素。
>   - 使用方括号 `[]` 创建，元素之间用逗号 `,` 分隔。
>   ```python
>   my_list = [1, 2, 3, 'four', 5.0]
>   ```
>
>2. **元组（Tuple）:**
>   - 类似于列表，但是是不可变的（immutable）。
>   - 使用圆括号 `()` 创建，元素之间用逗号 `,` 分隔。
>   ```python
>   my_tuple = (1, 2, 3, 'four', 5.0)
>   ```
>
>3. **集合（Set）:**
>   - 用于存储无序且唯一的元素。
>   - 使用大括号 `{}` 创建，元素之间用逗号 `,` 分隔。
>   ```python
>   my_set = {1, 2, 3, 3, 4, 5}
>   ```
>
>4. **字典（Dictionary）:**
>   - 用于存储键值对（key-value）映射。
>   - 使用大括号 `{}` 创建，每个键值对之间用冒号 `:` 分隔，键和值用逗号 `,` 分隔。
>   ```python
>   my_dict = {'name': 'John', 'age': 30, 'city': 'New York'}
>   ```
>
>5. **字符串（String）:**
>   - 用于存储文本数据。
>   - 使用单引号 `''` 或双引号 `""` 创建。
>   ```python
>   my_string = 'Hello, World!'
>   ```
>
>6. **队列（Queue）:**
>   - 通过 `queue` 模块提供的 `Queue` 类实现，用于实现先进先出（FIFO）的数据结构。
>   ```python
>   from queue import Queue
>   my_queue = Queue()
>   ```
>
>7. **栈（Stack）:**
>   - 通过 `collections` 模块提供的 `deque` 类实现，用于实现后进先出（LIFO）的数据结构。
>   ```python
>   from collections import deque
>   my_stack = deque()
>   ```
>
>8. **堆（Heap）:**
>   - 通过 `heapq` 模块提供的函数实现，用于实现优先级队列。
>   ```python
>   import heapq
>   my_heap = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5]
>   heapq.heapify(my_heap)
>   ```
>
>9. **链表（Linked List）:**
>   - 可以通过自定义类实现，用于实现链式存储结构。
>   ```python
>   class Node:
>       def __init__(self, data):
>           self.data = data
>           self.next = None
>   ```
>
>这些数据结构提供了不同的特性和适用场景。选择合适的数据结构取决于具体的问题和需求。Python 还支持其他一些数据结构和模块，如堆栈、双向队列等。

---
### LINKS
1. [[Python/数据结构/列表/列表-简介|列表]]
2. [[Python/数据结构/集合/集合-简介|集合]]
3. [[Python/数据结构/元组/元组-简介|元组]]
4. [[Python/数据结构/字典/字典-简介|字典]]

