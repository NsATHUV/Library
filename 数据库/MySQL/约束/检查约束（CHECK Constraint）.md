---
tags:
  - MySQL/约束
  - 内容
aliases: 
日月: 2024-11-26
时分: 15:47
---
**检查约束（CHECK Constraint）** 用于限制字段中存储的值，以确保数据的合法性。它通过定义一个布尔表达式，在插入或更新数据时对字段值进行校验，只有满足条件的数据才能存储在数据库中。

---

### **1. 检查约束的特点**

- **数据合法性**：通过条件表达式确保字段数据符合业务规则。
- **灵活性强**：支持多种逻辑运算符（`>`, `<`, `=`, `AND`, `OR` 等）定义复杂规则。
- **字段级别与表级别**：可以为单个字段或多个字段设置检查条件。
- **性能消耗小**：约束检查直接由数据库执行，无需额外的应用逻辑。

---

### **2. 检查约束语法与操作**

#### **2.1 创建表时设置检查约束**

```sql
# 在创建表时定义检查约束
CREATE TABLE 表名 (
    字段名 数据类型 [约束],
    CHECK (布尔表达式)
);
```

**示例**：

```sql
CREATE TABLE students (
    student_id INT PRIMARY KEY AUTO_INCREMENT,
    age INT NOT NULL CHECK (age >= 18), -- 年龄必须大于等于 18
    gender CHAR(1) CHECK (gender IN ('M', 'F')) -- 性别必须为 'M' 或 'F'
);
```

**说明**：

- `CHECK` 后的布尔表达式定义了字段的有效范围。
- 插入或更新数据时，数据库会验证数据是否符合该表达式。

---

#### **2.2 表级别的检查约束**

```sql
# 在表级别定义检查约束
CREATE TABLE 表名 (
    字段名1 数据类型,
    字段名2 数据类型,
    CONSTRAINT 约束名 CHECK (布尔表达式)
);
```

**示例**：

```sql
CREATE TABLE employees (
    emp_id INT PRIMARY KEY AUTO_INCREMENT,
    salary DECIMAL(10, 2) NOT NULL,
    bonus DECIMAL(10, 2),
    CONSTRAINT chk_salary CHECK (bonus <= salary * 0.2) -- 奖金不得超过工资的 20%
);
```

**说明**：

- 表级别约束可以作用于多个字段。
- 需要为约束起一个名称（如 `chk_salary`）以便维护和管理。

---

#### **2.3 修改表添加检查约束**

```sql
# 修改表添加检查约束
ALTER TABLE 表名 ADD CONSTRAINT 约束名 CHECK (布尔表达式);
```

**示例**：

```sql
ALTER TABLE students ADD CONSTRAINT chk_age CHECK (age <= 60); -- 年龄不得超过 60 岁
```

---

#### **2.4 删除检查约束**

```sql
# 删除检查约束
ALTER TABLE 表名 DROP CONSTRAINT 约束名;
```

**示例**：

```sql
ALTER TABLE students DROP CONSTRAINT chk_age; -- 删除年龄检查约束
```

---

### **3. 检查约束的应用场景**

- **数据范围限制**：如年龄、价格、数量等字段的值必须在合理范围内。
- **枚举值校验**：确保字段值为预定义的选项之一。
- **字段间逻辑关系**：检查多个字段的相互依赖关系。

**示例**：

```sql
CREATE TABLE products (
    product_id INT PRIMARY KEY AUTO_INCREMENT,
    product_name VARCHAR(50) NOT NULL,
    stock INT NOT NULL CHECK (stock >= 0), -- 库存不能为负
    price DECIMAL(10, 2) NOT NULL CHECK (price > 0) -- 价格必须大于 0
);
```

---

### **4. 检查约束的优势**

- **减少错误**：避免非法数据插入数据库。
- **易于维护**：约束直接存储在数据库中，不依赖应用层逻辑。
- **性能优化**：数据库层面的检查速度快且高效。

---

### **5. 检查约束的局限性**

- **部分数据库不支持**：如 MySQL 早期版本（5.7 及之前）不支持检查约束，但 8.0 开始支持。
- **表达式限制**：某些复杂的逻辑无法通过 `CHECK` 表达式实现。
- **跨表限制**：检查约束无法直接验证字段值是否与其他表数据相关。

---

### **6. 完整操作示例**

#### **6.1 创建表时定义检查约束**

```sql
CREATE TABLE orders (
    order_id INT PRIMARY KEY AUTO_INCREMENT,
    quantity INT NOT NULL CHECK (quantity > 0), -- 数量必须大于 0
    order_status VARCHAR(20) NOT NULL CHECK (order_status IN ('Pending', 'Shipped', 'Delivered')) -- 订单状态限制
);
```

#### **6.2 修改表添加检查约束**

```sql
ALTER TABLE orders ADD CONSTRAINT chk_total CHECK (quantity <= 100); -- 数量不能超过 100
```

#### **6.3 删除检查约束**

```sql
ALTER TABLE orders DROP CONSTRAINT chk_total; -- 删除数量检查约束
```

---

通过使用检查约束，可以有效管理字段值的合法性，避免非法数据进入数据库，从而提升数据质量与应用可靠性！