---
tags:
  - JavaScript
  - 内容
aliases: 
日月: 2024-12-03
时分: 00:28
---
### **JavaScript 条件语句**

条件语句根据不同的条件执行不同的代码块，是程序逻辑控制的核心。常见的条件语句包括 `if-else` 和 `switch`。

---

### **1. `if-else` 语句**

`if-else` 语句根据条件是否为 `true` 来执行代码块。

#### **语法**

```javascript
if (条件) {
    // 条件为 true 时执行的代码
} else if (其他条件) {
    // 第一个条件为 false 且其他条件为 true 时执行的代码
} else {
    // 上述所有条件都为 false 时执行的代码
}
```

#### **示例**

```javascript
let age = 20;

if (age < 18) {
    console.log("未成年");
} else if (age >= 18 && age < 60) {
    console.log("成年人");
} else {
    console.log("老年人");
}
```

#### **嵌套 `if` 语句**

`if` 语句可以嵌套使用：

```javascript
let score = 85;

if (score >= 60) {
    if (score >= 90) {
        console.log("优秀");
    } else {
        console.log("及格");
    }
} else {
    console.log("不及格");
}
```

---

### **2. `switch` 语句**

`switch` 语句根据变量的值选择要执行的代码块。它适用于多个值的精确匹配。

#### **语法**

```javascript
switch (表达式) {
    case 值1:
        // 匹配值1时执行的代码
        break; // 跳出 switch 语句
    case 值2:
        // 匹配值2时执行的代码
        break;
    default:
        // 当没有匹配的 case 时执行的代码
}
```

#### **示例**

```javascript
let day = 3;

switch (day) {
    case 1:
        console.log("星期一");
        break;
    case 2:
        console.log("星期二");
        break;
    case 3:
        console.log("星期三");
        break;
    default:
        console.log("未知日期");
}
```

#### **特点**

- `switch` 匹配的值必须是严格相等（`===`）。
- `break` 用于跳出 `switch` 语句，否则会继续执行后续的代码块（即“贯穿效应”）。

---

### **3. `if-else` vs `switch`**

|**特点**|**`if-else`**|**`switch`**|
|---|---|---|
|**适用场景**|处理复杂的条件判断|处理多个值的精确匹配|
|**可读性**|条件复杂时代码可变得难以阅读|条件较多时代码更整洁|
|**灵活性**|支持范围、逻辑表达式|仅支持值匹配|
|**执行效率**|对简单条件判断效率较高|对多个条件匹配时效率更高|

---

### **4. 嵌套和组合示例**

结合使用 `if-else` 和 `switch` 语句：

```javascript
let userRole = "admin";

if (userRole === "admin" || userRole === "manager") {
    let action = "delete";

    switch (action) {
        case "view":
            console.log("查看权限");
            break;
        case "edit":
            console.log("编辑权限");
            break;
        case "delete":
            console.log("删除权限");
            break;
        default:
            console.log("无权限");
    }
} else {
    console.log("访问受限");
}
```

---

### **5. 小结**

- `if-else` 适用于复杂逻辑判断。
- `switch` 适用于多个值的精确匹配。
- 在选择使用哪种条件语句时，应根据逻辑复杂性和代码的可读性进行权衡。