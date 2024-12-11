---
tags:
  - JAVA/JAVA_WEB/JSP
  - 内容
aliases:
  - EL
  - Expression Language
日月: 2024-11-21
时分: 15:35
---
**EL表达式（Expression Language）** 是 JSP（Java Server Pages）中的一种表达式语言，主要用于简化 JSP 页面的编程操作，减少 Java 代码的嵌入，使页面更加简洁易读。EL 表达式以 `${}` 语法标记开头，能够方便地访问 Java 对象的属性、集合以及常用的隐式对象。

### **EL表达式的功能**

1. **访问JavaBean的属性**  
    可以通过点语法直接访问对象的属性。
    
    ```jsp
    ${user.name}  <!-- 访问 user 对象的 name 属性 -->
    ```
    
2. **访问Map中的值**  
    可以通过键值对的键来获取值。
    
    ```jsp
    ${map['key']}  <!-- 访问 map 中 key 对应的值 -->
    ```
    
3. **访问集合元素**  
    可以通过索引访问 List 或数组中的元素。
    
    ```jsp
    ${list[0]}     <!-- 访问 list 中第一个元素 -->
    ${array[1]}    <!-- 访问数组中第二个元素 -->
    ```
    
4. **调用隐式对象**  
    JSP 中的 EL 提供了一些隐式对象，用于简化获取请求、会话、应用范围的数据。例如：
    
    - `pageScope`：页面范围的属性。
    - `requestScope`：请求范围的属性。
    - `sessionScope`：会话范围的属性。
    - `applicationScope`：应用范围的属性。
    
    ```jsp
    ${sessionScope.user}  <!-- 获取会话范围的 user 属性 -->
    ```
    
5. **逻辑运算**  
    支持逻辑判断和三元运算符。
    
    ```jsp
    ${user.age > 18 ? '成年' : '未成年'}  <!-- 三元运算符 -->
    ${user != null}                       <!-- 非空判断 -->
    ```
    
6. **常量值**  
    可以访问常见的常量值，如布尔值、空值等。
    
    ```jsp
    ${true}  ${false}  ${null}
    ```
    

### **EL表达式的优点**

- **简洁**：用表达式代替大量的 Java 代码。
- **易读**：提高了 JSP 页面的可读性和可维护性。
- **安全**：自动进行类型转换和空值检查，避免空指针异常。

### **在JSP中启用EL表达式**

默认情况下，JSP 2.0 及以上版本已启用 EL 表达式。如果 EL 表达式被禁用，可以在 JSP 文件头部添加以下指令启用：

```jsp
<%@ page isELIgnored="false" %>
```

### **EL表达式和 JSTL 的结合**

EL 表达式经常与 JSTL（JavaServer Pages Standard Tag Library）一起使用，实现页面逻辑与数据操作分离。  
例如：

```jsp
<c:if test="${user.age > 18}">
    欢迎，成年人！
</c:if>
```

通过 EL 表达式，可以轻松地在 JSP 页面中绑定动态数据，极大地提高了开发效率。