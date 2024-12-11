---
tags:
  - MySQL/约束
  - 内容
aliases:
  - 主键
  - 主键自增长
  - 自增长
日月: 2024-11-24
时分: 21:08
---
**主键约束（Primary Key Constraint）** 是用于唯一标识表中每一行数据的一种数据库完整性约束。合理使用主键约束可以保证数据的唯一性和完整性，并提升查询效率。

### **1. 主键的特点**

- **唯一性**：主键列的值必须唯一，不能重复。
- **非空性**：主键列的值不能为 `NULL`。
- **单一性**：每张表只能定义一个主键。
- **自动索引**：MySQL 自动为主键列创建唯一索引。

---

### **2. 主键语法与操作**

#### **2.1 设置单字段主键**

```sql
# 设置单字段主键
<字段名> <数据类型> PRIMARY KEY [默认值];
```

**示例**：

```sql
CREATE TABLE students (
    id INT PRIMARY KEY AUTO_INCREMENT, -- 将 id 设置为主键并自动递增
    name VARCHAR(50) NOT NULL,
    age INT
);
```

**说明**：

- 使用 `PRIMARY KEY` 将字段定义为主键。
- `AUTO_INCREMENT` 属性可自动递增主键值。
- 主键字段必须唯一且非空。

---

#### **2.2 创建表时设置联合主键**

```sql
# 设置联合主键
CREATE TABLE 表名(
    字段1 数据类型 [约束],
    字段2 数据类型 [约束],
    ...
    PRIMARY KEY ([字段1, 字段2, ...])
);
```

**示例**：

```sql
CREATE TABLE enrollment (
    student_id INT NOT NULL,
    course_id INT NOT NULL,
    enroll_date DATE,
    PRIMARY KEY (student_id, course_id) -- 联合主键
);
```

**说明**：

- 联合主键由多个字段组成，要求这些字段的组合值唯一。
- 常用于多对多关系的中间表，确保记录唯一性。

---

#### **2.3 修改表添加主键**

```sql
# 添加主键
ALTER TABLE <数据表名> ADD PRIMARY KEY (<字段名>);
```

**示例**：

```sql
ALTER TABLE students ADD PRIMARY KEY (id); -- 添加单字段主键
ALTER TABLE enrollment ADD PRIMARY KEY (student_id, course_id); -- 添加联合主键
```

**说明**：

- 使用 `ALTER TABLE` 为已存在的表添加主键。
- 若表中已有重复数据或 `NULL` 值，添加主键会失败。

---

#### **2.4 删除主键**

```sql
# 删除主键
ALTER TABLE <数据表名> DROP PRIMARY KEY;
```

**示例**：

```sql
ALTER TABLE students DROP PRIMARY KEY; -- 删除主键
```

**说明**：

- 删除主键后，主键字段将失去唯一性和非空约束。
- 如果主键字段设置了 `AUTO_INCREMENT`，删除主键后需手动移除该属性。

---
### 3. [主键自增长](http://c.biancheng.net/view/7624.html#:~:text=MySQL%20AUTO_INCREMENT%EF%BC%9A-,%E4%B8%BB%E9%94%AE%E8%87%AA%E5%A2%9E%E9%95%BF,-%3C%20%E4%B8%8A%E4%B8%80%E8%8A%82)


   当主键定义为自增长后，这个主键的值就不再需要用户输入数据了，而由数据库系统根据定义自动赋值。每增加一条记录，主键会自动以相同的步长进行增长。

- 默认情况下，`AUTO_INCREMENT` 的初始值是 1，每新增一条记录，字段值自动加 1。
- 一个表中只能有一个字段使用 `AUTO_INCREMENT` 约束，且该字段必须有唯一索引，以避免序号重复（即为主键或主键的一部分）。
- `AUTO_INCREMENT` 约束的字段必须具备 `NOT NULL` 属性。
- `AUTO_INCREMENT` 约束的字段只能是整数类型（`TINYINT`、`SMALLINT`、`INT`、`BIGINT` 等）。
- `AUTO_INCREMENT` 约束字段的最大值受该字段的数据类型约束，如果达到上限，`AUTO_INCREMENT` 就会失效。

```SQL
# 创建表时设置主键自增长
<字段名> <数据类型> (PRIME KEY)AUTO_INCREMENT
```



---

### **4. 主键设计建议**

- 使用简单整数作为主键，推荐 `AUTO_INCREMENT`，避免手动操作。
- 控制联合主键的字段数量，过多字段会增加复杂性。
- 避免使用实际业务数据（如身份证号、手机号码）作为主键，因为这些数据可能会发生变更。
- 若使用 UUID 作为主键，需考虑其对性能的影响（索引效率较低）。

---

### **5. 主键与其他约束的关系**

- **主键与唯一约束**：
    - 主键隐式包含唯一约束（`UNIQUE`）。
    - 唯一约束允许 `NULL` 值，但主键不允许。
- **主键与外键**：
    - 主键常作为其他表中外键的参照，用于建立表之间的关系。

---

### **6. 完整操作示例**

#### **6.1 创建表时设置主键**

```sql
CREATE TABLE employees (
    emp_id INT PRIMARY KEY AUTO_INCREMENT,
    name VARCHAR(50) NOT NULL,
    position VARCHAR(50)
);
```

#### **6.2 添加联合主键**

```sql
CREATE TABLE project_assignment (
    emp_id INT NOT NULL,
    project_id INT NOT NULL,
    PRIMARY KEY (emp_id, project_id)
);
```

#### **6.3 修改表添加主键**

```sql
ALTER TABLE projects ADD PRIMARY KEY (project_id);
```

#### **6.4 删除主键**

```sql
ALTER TABLE projects DROP PRIMARY KEY;
```

---

通过这些语法和设计规范，可以高效地管理 MySQL 中的主键约束，保证数据完整性与唯一性！