---
tags:
  - JAVA/内容
aliases: 
日月: 2024-04-24
时分: 11:02
---
在Java中，`==`运算符和`equals()`方法都用于比较两个对象，但它们之间有很大的区别：

1. `==`运算符：
   - `==`运算符比较的是两个对象的引用（内存地址），而不是它们的内容。
   - 对于基本数据类型（如`int`, `char`, `float`等），`==`比较的是值。
   - 对于引用类型（如对象），`==`比较的是两个对象是否引用同一块内存地址。

   示例：
   ```java
   String str1 = new String("hello");
   String str2 = new String("hello");
   String str3 = str1;

   System.out.println(str1 == str2);  // 输出false，因为它们是两个不同的对象
   System.out.println(str1 == str3);  // 输出true，因为它们引用同一块内存地址
   ```

2. `equals()`方法：
   - `equals()`方法用于比较两个对象的内容是否相等。
   - 默认情况下，`Object`类中的`equals()`方法是使用`==`运算符实现的，因此它与`==`具有相同的行为。但是，许多Java类（如`String`, `Integer`, `Double`等）重写了`equals()`方法，以便比较对象的内容而不是引用。

   示例：
   ```java
   String str1 = new String("hello");
   String str2 = new String("hello");

   System.out.println(str1.equals(str2));  // 输出true，因为它们的内容相同
   ```

总结：
- 使用`==`运算符进行对象比较时，你通常比较的是对象的引用。
- 使用`equals()`方法进行对象比较时，你通常比较的是对象的内容。但是，你应该注意，除非类重写了`equals()`方法，否则它默认使用`==`进行比较。