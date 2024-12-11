---
tags:
  - MySQL/约束
  - 内容
aliases: 
日月: 2024-11-26
时分: 15:37
---
**非空约束（NOT NULL Constraint）** 是一种限制字段值不能为空的完整性约束。通过非空约束，可以确保数据库中的关键字段总是有值，从而避免数据的不完整性。

---

### **1. 非空约束的特点**

- **字段必填**：非空约束确保字段不能存储 `NULL` 值。
- **默认约束**：可以结合默认值（`DEFAULT`）一起使用，确保字段具有合理的初始值。
- **提升数据质量**：避免因缺失数据而导致的业务逻辑问题。
- **兼容性**：适用于几乎所有数据类型。

---

### **2. 非空约束语法与操作**

#### **2.1 创建表时设置非空约束**

```sql
# 在创建表时定义非空约束
CREATE TABLE 表名 (
    字段名 数据类型 NOT NULL
);
```

**示例**：

```sql
CREATE TABLE users (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(50) NOT NULL, -- 设置非空
    email VARCHAR(100)
);
```

**说明**：

- `NOT NULL` 用于指定字段不能为空。
- 非空字段必须在插入数据时提供值。

---

#### **2.2 修改表添加非空约束**

```sql
# 修改表添加非空约束
ALTER TABLE 表名 MODIFY COLUMN 字段名 数据类型 NOT NULL;
```

**示例**：

```sql
ALTER TABLE users MODIFY COLUMN email VARCHAR(100) NOT NULL; -- 为 email 字段添加非空约束
```

**说明**：

- 在修改表时，使用 `MODIFY COLUMN` 添加非空约束。
- 目标字段中不能有 `NULL` 值，否则会报错。

---

#### **2.3 删除非空约束**

```sql
# 删除非空约束
ALTER TABLE 表名 MODIFY COLUMN 字段名 数据类型;
```

**示例**：

```sql
ALTER TABLE users MODIFY COLUMN email VARCHAR(100); -- 删除 email 字段的非空约束
```

**说明**：

- 使用 `MODIFY COLUMN` 并省略 `NOT NULL` 来移除非空约束。
- 移除非空约束后，字段可以存储 `NULL` 值。

---

### **3. 非空约束的应用场景**

- **用户系统**：
    - 用户名、密码等关键字段不能为空。
- **订单管理**：
    - 订单时间、客户信息等字段必须有值。
- **业务字段**：
    - 业务中重要的非可选字段需要确保有值。

**示例**：

```sql
CREATE TABLE orders (
    order_id INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT NOT NULL, -- 客户 ID 必填
    order_date DATE NOT NULL, -- 订单日期必填
    status VARCHAR(20) DEFAULT 'Pending' -- 状态字段允许空值，有默认值
);
```

---

### **4. 非空约束的优势**

- **强制数据完整性**：防止字段值缺失，确保业务逻辑正常运行。
- **简化数据验证**：数据库层面直接限制空值，减少应用层代码。
- **适用性广**：可与其他约束（如主键、唯一约束等）结合使用。

---

### **5. 非空约束与其他约束的关系**

- **与主键的关系**：
    - 主键字段隐含非空约束，因为主键必须唯一且不能为空。
    - 手动设置非空约束不影响主键功能。
- **与唯一约束的关系**：
    - 唯一约束字段允许 `NULL` 值，非空约束则强制字段有值。
    - 可同时设置唯一约束和非空约束。

**示例**：

```sql
CREATE TABLE products (
    product_id INT PRIMARY KEY AUTO_INCREMENT,
    product_code VARCHAR(50) NOT NULL UNIQUE -- 既唯一又非空
);
```

---

### **6. 完整操作示例**

#### **6.1 创建表时定义非空约束**

```sql
CREATE TABLE customers (
    customer_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50) NOT NULL, -- 姓名必填
    email VARCHAR(100) NOT NULL, -- 邮箱必填
    phone VARCHAR(15) -- 电话号码可为空
);
```

#### **6.2 修改表添加非空约束**

```sql
ALTER TABLE customers MODIFY COLUMN phone VARCHAR(15) NOT NULL; -- 将 phone 字段设置为非空
```

#### **6.3 删除非空约束**

```sql
ALTER TABLE customers MODIFY COLUMN phone VARCHAR(15); -- 允许 phone 字段为空
```

---

通过非空约束，可以确保数据库中关键字段始终有值，从而提高数据的完整性和准确性！