---
tags: 
aliases: 
日月: 2024-11-26
时分: 15:44
---
**默认值约束（DEFAULT Constraint）** 是一种用于指定字段默认值的完整性约束。当插入数据时，如果某个字段未明确赋值，则数据库会自动为其填充默认值。这不仅提高了操作的简便性，还确保了数据的一致性。

---

### **1. 默认值约束的特点**

- **自动填充**：在插入数据时，未赋值的字段会自动取默认值。
- **减少代码**：无需在每次插入时显式提供值。
- **数据一致性**：为字段提供合理的默认值，防止数据缺失或异常。
- **灵活性**：可以结合 `NOT NULL` 或其他约束使用，确保字段有值。

---

### **2. 默认值约束语法与操作**

#### **2.1 创建表时设置默认值**

```sql
# 在创建表时定义默认值约束
CREATE TABLE 表名 (
    字段名 数据类型 DEFAULT 默认值
);
```

**示例**：

```sql
CREATE TABLE orders (
    order_id INT PRIMARY KEY AUTO_INCREMENT,
    order_status VARCHAR(20) DEFAULT 'Pending', -- 设置默认值为 "Pending"
    order_date DATE DEFAULT CURRENT_DATE -- 默认值为当前日期
);
```

**说明**：

- 使用 `DEFAULT` 关键字定义字段的默认值。
- 默认值可以是常量（如字符串、数字）或表达式（如 `CURRENT_DATE`）。

---

#### **2.2 修改表添加默认值**

```sql
# 修改表添加默认值
ALTER TABLE 表名 MODIFY COLUMN 字段名 数据类型 DEFAULT 默认值;
```

**示例**：

```sql
ALTER TABLE orders MODIFY COLUMN order_status VARCHAR(20) DEFAULT 'Processing'; -- 修改字段默认值
```

**说明**：

- 使用 `MODIFY COLUMN` 指定字段默认值。
- 如果字段已有数据，默认值不会影响现有记录，仅对新插入的记录生效。

---

#### **2.3 删除默认值**

```sql
# 删除默认值
ALTER TABLE 表名 MODIFY COLUMN 字段名 数据类型;
```

**示例**：

```sql
ALTER TABLE orders MODIFY COLUMN order_status VARCHAR(20); -- 移除默认值
```

**说明**：

- 省略 `DEFAULT` 关键字即可移除字段的默认值。
- 删除默认值后，插入时如果不赋值会存储 `NULL`（若字段允许空值）。

---

### **3. 默认值约束的应用场景**

- **状态管理**：为订单状态、用户状态等设置默认值（如 `Pending`、`Active`）。
- **时间字段**：为记录创建或更新时间的字段设置默认值（如 `CURRENT_TIMESTAMP`）。
- **计数与统计**：为计数字段初始化为 `0`。
- **选项字段**：为字段设置默认选项值（如 `Male` 或 `Female`）。

**示例**：

```sql
CREATE TABLE users (
    user_id INT PRIMARY KEY AUTO_INCREMENT,
    username VARCHAR(50) NOT NULL,
    user_status VARCHAR(20) DEFAULT 'Active', -- 默认状态为 "Active"
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP -- 默认值为当前时间
);
```

---

### **4. 默认值约束的优势**

- **提升效率**：减少插入数据时的显式赋值操作。
- **确保一致性**：避免因缺省值导致的业务逻辑错误。
- **优化存储**：字段未赋值时自动填充合理的默认值。

---

### **5. 默认值与其他约束的关系**

- **与非空约束**：
    - 默认值可以与非空约束结合使用。
    - 如果字段为 `NOT NULL` 且没有默认值，插入数据时必须显式赋值。
- **与主键约束**：
    - 主键字段通常不能有默认值（如自增字段）。
- **与唯一约束**：
    - 默认值与唯一约束冲突时，需确保默认值在表中唯一。

**示例**：

```sql
CREATE TABLE products (
    product_id INT PRIMARY KEY AUTO_INCREMENT,
    product_name VARCHAR(50) NOT NULL,
    stock INT DEFAULT 0 NOT NULL, -- 默认值为 0 且不能为空
    price DECIMAL(10, 2) NOT NULL
);
```

---

### **6. 完整操作示例**

#### **6.1 创建表时定义默认值**

```sql
CREATE TABLE employees (
    emp_id INT PRIMARY KEY AUTO_INCREMENT,
    emp_name VARCHAR(50) NOT NULL,
    emp_status VARCHAR(20) DEFAULT 'Active', -- 默认状态为 "Active"
    hire_date DATE DEFAULT CURRENT_DATE -- 默认值为当前日期
);
```

#### **6.2 修改表添加默认值**

```sql
ALTER TABLE employees MODIFY COLUMN emp_status VARCHAR(20) DEFAULT 'On Leave'; -- 修改默认值
```

#### **6.3 删除默认值**

```sql
ALTER TABLE employees MODIFY COLUMN emp_status VARCHAR(20); -- 移除默认值
```

---

通过合理设置默认值约束，可以简化操作、提高数据完整性并优化数据库管理的效率！