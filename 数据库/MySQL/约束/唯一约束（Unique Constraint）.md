---
tags:
  - MySQL/约束
  - 内容
aliases: 
日月: 2024-11-26
时分: 15:36
---

**唯一约束（Unique Constraint）** 是一种保证数据库表中某个字段或字段组合的值具有唯一性的完整性约束。通过唯一约束，可以确保字段的值不重复，从而避免数据冗余或冲突。

---

### **1. 唯一约束的特点**

- **值唯一**：同一张表中，唯一约束字段的值必须唯一，但允许 `NULL` 值。
- **数据完整性**：用于保证关键数据的唯一性，例如用户名、电子邮件地址等。
- **自动索引**：唯一约束字段会自动创建唯一索引，提高查询效率。
- **多字段组合**：可以对多个字段设置联合唯一约束。

---

### **2. 唯一约束语法与操作**

#### **2.1 创建表时设置唯一约束**

```sql
# 在创建表时定义唯一约束
CREATE TABLE 表名 (
    字段名 数据类型 [约束],
    CONSTRAINT 约束名 UNIQUE (字段名)
);
```

**示例**：

```sql
CREATE TABLE users (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(50) NOT NULL,
    email VARCHAR(100),
    CONSTRAINT unique_email UNIQUE (email) -- 设置 email 字段为唯一
);
```

**说明**：

- 使用 `CONSTRAINT` 明确指定唯一约束的名称，方便后续管理。
- 字段设置为唯一时，不同记录中不能出现重复值。

---

#### **2.2 修改表添加唯一约束**

```sql
# 修改表添加唯一约束
ALTER TABLE 表名 ADD CONSTRAINT 约束名 UNIQUE (字段名);
```

**示例**：

```sql
ALTER TABLE users ADD CONSTRAINT unique_email UNIQUE (email); -- 为 email 字段添加唯一约束
```

**说明**：

- 在已存在的表中，可通过 `ALTER TABLE` 添加唯一约束。
- 唯一约束的字段不允许已有重复值。

---

#### **2.3 删除唯一约束**

```sql
# 删除唯一约束
ALTER TABLE 表名 DROP INDEX 约束名;
```

**示例**：

```sql
ALTER TABLE users DROP INDEX unique_email; -- 删除 email 字段的唯一约束
```

**说明**：

- 唯一约束在底层是通过唯一索引实现的，因此删除唯一约束时使用 `DROP INDEX`。

---

### **3. 唯一约束的应用场景**

- **用户管理系统**：限制用户名或邮箱地址的唯一性。
- **订单管理系统**：确保订单号或交易编号唯一。
- **联合唯一约束**：组合多个字段来限定记录唯一性，例如学生的学号和考试科目联合唯一。

**示例**：

```sql
CREATE TABLE student_scores (
    student_id INT,
    course_id INT,
    score FLOAT,
    CONSTRAINT unique_score UNIQUE (student_id, course_id) -- 学生和课程的组合唯一
);
```

---

### **4. 唯一约束的优势**

- **保证数据一致性**：防止关键字段出现重复值。
- **简化数据验证**：数据库层面直接限制数据的唯一性，无需额外代码逻辑。
- **提升查询效率**：自动生成的唯一索引可以优化查询性能。

---

### **5. 唯一约束与其他约束的关系**

- **与主键的关系**：
    
    - 主键本质上也是一种唯一约束，但主键字段不允许 `NULL`，而唯一约束允许 `NULL`。
    - 一个表中只能有一个主键，但可以有多个唯一约束。
- **与索引的关系**：
    
    - 唯一约束自动生成唯一索引，功能类似于直接创建唯一索引。
    - 索引侧重于查询优化，而唯一约束同时具备完整性约束的功能。

---

### **6. 完整操作示例**

#### **6.1 创建表时设置唯一约束**

```sql
CREATE TABLE products (
    product_id INT PRIMARY KEY AUTO_INCREMENT,
    product_code VARCHAR(50) NOT NULL,
    product_name VARCHAR(100),
    CONSTRAINT unique_code UNIQUE (product_code) -- 限制 product_code 唯一
);
```

#### **6.2 修改表添加唯一约束**

```sql
ALTER TABLE products ADD CONSTRAINT unique_code UNIQUE (product_code);
```

#### **6.3 删除唯一约束**

```sql
ALTER TABLE products DROP INDEX unique_code;
```

---

通过合理使用唯一约束，可以有效避免数据冲突，维护数据库的完整性和规范性！