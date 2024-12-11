---
tags:
  - MySQL/约束
  - 内容
aliases:
  - 外键
日月: 2024-11-24
时分: 21:34
---
**外键约束（Foreign Key Constraint）** 是用于维护数据库中表与表之间关系的一种完整性约束。通过外键，可以确保一个表中的字段值必须在另一张表中存在，从而保证数据的参照完整性。

---

### **1. 外键的特点**

- **参照完整性**：外键列的值必须在参照表的主键或唯一键列中存在。
- **连接关系**：外键用来表示两个表之间的逻辑关联。
- **多对一约束**：一个表中的外键可以指向另一个表的主键。
- **级联操作**：可以指定删除或更新时的级联规则。

---

### **2. 外键语法与操作**

#### **2.1 创建表时设置外键**

```sql
# 创建表时设置外键
CREATE TABLE 表名 (
    字段名 数据类型 [约束],
    FOREIGN KEY (字段名) REFERENCES 参照表名 (参照字段名)
    [ON DELETE <级联规则>] [ON UPDATE <级联规则>]
);
```

**示例**：

```sql
CREATE TABLE orders (
    order_id INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT,
    order_date DATE,
    FOREIGN KEY (customer_id) REFERENCES customers(customer_id) -- 设置外键
    ON DELETE CASCADE -- 删除客户时删除相关订单
    ON UPDATE CASCADE -- 更新客户主键时同步更新
);
```

**说明**：

- 使用 `FOREIGN KEY` 定义外键约束。
- `REFERENCES` 指定参照表及字段，通常参照字段是主键或唯一键。
- `ON DELETE` 和 `ON UPDATE` 指定级联操作（详见下文）。

---

#### **2.2 修改表添加外键**

```sql
# 修改表添加外键
ALTER TABLE 表名 ADD CONSTRAINT 外键名 FOREIGN KEY (字段名) REFERENCES 参照表名 (参照字段名)
[ON DELETE <级联规则>] [ON UPDATE <级联规则>];
```

**示例**：

```sql
ALTER TABLE orders
ADD CONSTRAINT fk_customer FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
ON DELETE CASCADE
ON UPDATE CASCADE;
```

**说明**：

- `ADD CONSTRAINT` 语法为已存在的表添加外键约束。
- 外键名 `fk_customer` 是可选的，建议自定义以便管理。

---

#### **2.3 删除外键**

```sql
# 删除外键
ALTER TABLE 表名 DROP FOREIGN KEY 外键名;
```

**示例**：

```sql
ALTER TABLE orders DROP FOREIGN KEY fk_customer; -- 删除外键
```

**说明**：

- 删除外键后，表之间的参照关系将不再受约束。

---

### **3. 外键的级联规则**

- **`CASCADE`**：
    
    - **`ON DELETE CASCADE`**：删除父表记录时，自动删除子表中对应的记录。
    - **`ON UPDATE CASCADE`**：更新父表主键时，自动更新子表中对应的外键值。
- **`SET NULL`**：
    
    - **`ON DELETE SET NULL`**：删除父表记录时，将子表中对应的外键值设置为 `NULL`。
    - **`ON UPDATE SET NULL`**：更新父表主键时，将子表中对应的外键值设置为 `NULL`。
- **`RESTRICT`**：
    
    - 禁止删除或更新父表中有子表依赖的记录。
- **`NO ACTION`**：
    
    - 与 `RESTRICT` 类似，但执行检查时稍有不同。

---

### **4. 外键设计建议**

- 确保外键字段与参照字段的数据类型一致。
- 为外键字段创建索引以提高查询性能。
- 尽量为外键命名，方便维护和管理。
- 避免过度依赖外键约束来保证数据完整性，可以结合应用层逻辑处理。

---

### **5. 外键与其他约束的关系**

- **外键与主键**：
    - 外键通常指向另一表的主键。
    - 外键值必须匹配父表中的主键值或为空（若允许 `NULL`）。
- **外键与唯一键**：
    - 外键也可以指向参照表的唯一键字段。
- **外键与索引**：
    - 外键字段在子表中自动建立索引以优化查询效率。

---

### **6. 完整操作示例**

#### **6.1 创建表时定义外键**

```sql
CREATE TABLE customers (
    customer_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50) NOT NULL
);

CREATE TABLE orders (
    order_id INT PRIMARY KEY AUTO_INCREMENT,
    customer_id INT,
    order_date DATE,
    FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
    ON DELETE CASCADE
    ON UPDATE CASCADE
);
```

#### **6.2 修改表添加外键**

```sql
ALTER TABLE orders
ADD CONSTRAINT fk_customer FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
ON DELETE SET NULL
ON UPDATE CASCADE;
```

#### **6.3 删除外键**

```sql
ALTER TABLE orders DROP FOREIGN KEY fk_customer;
```

---

通过这些语法和设计规范，可以有效管理 MySQL 中的外键约束，保证表与表之间的数据一致性与完整性！