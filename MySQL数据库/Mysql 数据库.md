# 数据库笔记-蔡金良

## 笔记事项

>   #### 这是分节式的笔记，不能从头看到尾，正确的方法是想要查看什么内容，通过索引查找，就像看词典。
>
>   -   若图片无法查看，请确定 [Mysql 数据库.assets] 该文件夹存在并且与HTML文件在同一个文件夹下。（直接从压缩包解压就不会出现图片丢失的问题）
>   -   标有“@”符号的内容，可以使用鼠标中键点击，跳转至参考链接，通常会得到更加详细的讲解。请不要使用鼠标左键点击，会覆盖掉笔记。使用中键点击会从新标签打开。



# 基础

## 数据库的基本概念

>   QQ：聊天
>
>   Word：写文档
>
>   数据库：存放数据的仓库，存放学生的信息，图书的信息，用户的信息，订单的信息……
>
>   数据表：数据中存放着一张表
>
>   数据库的种类：MySQL、Oracle、SQL Sever等

>   数据库的特点：
>
>   1.  持久化存储数据。
>   2.  方便存储和管理数据
>   3.  使用了统一的方式操作数据库——SQL脚本

> ###### 关系型数据库：
>
> - 从用户角度，关系模型中数据的逻辑结构是一张二维表。
> - 表是关系数据库的基本存储单位。
> - 现实中的每一个对象都可以抽象为表来进行存储。
>
> **数据库由表组成**

## 数据表的基本概念

> ### 记录（行）
>
> -   **表中的一行称为一个记录。**一个记录的内容是描述一类事物中的一个具体事物的一组数据如一个雇员的编号、姓名、工资数目。

> ### 字段（列）
>
> -   **表中的一列称为一个字段。**每个字段表示表中所描述的对象和一个属性
>
> -   每个字段都有相应的描述信息，如字段名、数据类型、数据宽度、数值型数据的小数位数等。
>
> ![image-20230511231333239](./Mysql%20%E6%95%B0%E6%8D%AE%E5%BA%93.assets/image-20230511231333239.png)





## MySQL

> ​	MySQL是一种关系型数据库管理系统，[关系数据库](https://baike.baidu.com/item/%E5%85%B3%E7%B3%BB%E6%95%B0%E6%8D%AE%E5%BA%93/1237340?fromModule=lemma_inlink)将数据保存在不同的表中，而不是将所有数据放在一个大仓库内，这样就增加了速度并提高了灵活性。

## SQLYOG

>   SQLyog 是一个易于使用的、快速而简洁的图形化管理 MYSQL 数据库的工具，它能够在任何地点有效地管理你的数据库。

### 新建数据库

>   ##### 点击新连接
>![[./Mysql%20%E6%95%B0%E6%8D%AE%E5%BA%93.assets/image-20230508141401518.png]]
>   <img src="./Mysql%20%E6%95%B0%E6%8D%AE%E5%BA%93.assets/image-20230508141401518.png" alt="image-20230508141401518" style="zoom:67%;" />

### 创建一个名为School的新连接

>   <img src="./Mysql%20%E6%95%B0%E6%8D%AE%E5%BA%93.assets/image-20230508142758795.png" alt="image-20230508142758795" style="zoom: 60%;" />

### 创建名为Student的数据库

>   1.  右键左侧区域
>   2.  选择创建数据库
>
>   或者
>
>   1.  使用快捷键：**`CTRL`**+**`D`**

>   <img src="./Mysql%20%E6%95%B0%E6%8D%AE%E5%BA%93.assets/image-20230508143148786.png" alt="image-20230508143148786" style="zoom:67%;" />

------

## 查看本机IP

>   -   方法1：CMD → `ipconfig`
>   -   方法2：通过“网络”图标查看IP地址
>       -   1）控制面板→“网络”→适配器
>       -   2）右键→属性 →TCP/IPV4→属性

# 数据类型[^1]

## [数值类型](https://www.runoob.com/mysql/mysql-data-types.html# :~:text=%E4%B8%B2(%E5%AD%97%E7%AC%A6)%E7%B1%BB%E5%9E%8B%E3%80%82-,%E6%95%B0%E5%80%BC%E7%B1%BB%E5%9E%8B,-MySQL%20%E6%94%AF%E6%8C%81%E6%89%80%E6%9C%89)

|     类型     |                   大小                   |                        范围（有符号）                        |                        范围（无符号）                        |      用途       |
| :----------: | :--------------------------------------: | :----------------------------------------------------------: | :----------------------------------------------------------: | :-------------: |
|   TINYINT    |                 1 Bytes                  |                         (-128，127)                          |                           (0，255)                           |    小整数值     |
|   SMALLINT   |                 2 Bytes                  |                      (-32 768，32 767)                       |                         (0，65 535)                          |    大整数值     |
|  MEDIUMINT   |                 3 Bytes                  |                   (-8 388 608，8 388 607)                    |                       (0，16 777 215)                        |    大整数值     |
| INT或INTEGER |                 4 Bytes                  |               (-2 147 483 648，2 147 483 647)                |                      (0，4 294 967 295)                      |    大整数值     |
|    BIGINT    |                 8 Bytes                  |   (-9,223,372,036,854,775,808，9 223 372 036 854 775 807)    |               (0，18 446 744 073 709 551 615)                |   极大整数值    |
|    FLOAT     |                 4 Bytes                  | (-3.402 823 466 E+38，-1.175 494 351 E-38)，0，(1.175 494 351 E-38，3.402 823 466 351 E+38) |         0，(1.175 494 351 E-38，3.402 823 466 E+38)          | 单精度 浮点数值 |
|    DOUBLE    |                 8 Bytes                  | (-1.797 693 134 862 315 7 E+308，-2.225 073 858 507 201 4 E-308)，0，(2.225 073 858 507 201 4 E-308，1.797 693 134 862 315 7 E+308) | 0，(2.225 073 858 507 201 4 E-308，1.797 693 134 862 315 7 E+308) | 双精度 浮点数值 |
|   DECIMAL    | 对DECIMAL(M,D) ，如果M>D，为M+2否则为D+2 |                        依赖于M和D的值                        |                        依赖于M和D的值                        |     小数值      |

## [日期和时间类型](https://www.runoob.com/mysql/mysql-data-types.html# :~:text=%E5%B0%8F%E6%95%B0%E5%80%BC-,%E6%97%A5%E6%9C%9F%E5%92%8C%E6%97%B6%E9%97%B4%E7%B1%BB%E5%9E%8B,-%E8%A1%A8%E7%A4%BA%E6%97%B6%E9%97%B4%E5%80%BC)

| 类型      | 大小 ( bytes) | 范围                                                         | 格式                | 用途                     |
| :-------- | :------------ | :----------------------------------------------------------- | :------------------ | :----------------------- |
| DATE      | 3             | 1000-01-01/9999-12-31                                        | YYYY-MM-DD          | 日期值                   |
| TIME      | 3             | '-838:59:59'/'838:59:59'                                     | HH:MM:SS            | 时间值或持续时间         |
| YEAR      | 1             | 1901/2155                                                    | YYYY                | 年份值                   |
| DATETIME  | 8             | '1000-01-01 00:00:00' 到 '9999-12-31 23:59:59'               | YYYY-MM-DD hh:mm:ss | 混合日期和时间值         |
| TIMESTAMP | 4             | '1970-01-01 00:00:01' UTC 到 '2038-01-19 03:14:07' UTC结束时间是第 **2147483647** 秒，北京时间 **2038-1-19 11:14:07**，格林尼治时间 2038年1月19日 凌晨 03:14:07 | YYYY-MM-DD hh:mm:ss | 混合日期和时间值，时间戳 |

## [字符串类型](https://www.runoob.com/mysql/mysql-data-types.html# :~:text=%E5%80%BC%EF%BC%8C%E6%97%B6%E9%97%B4%E6%88%B3-,%E5%AD%97%E7%AC%A6%E4%B8%B2%E7%B1%BB%E5%9E%8B,-%E5%AD%97%E7%AC%A6%E4%B8%B2%E7%B1%BB%E5%9E%8B)

| 类型       | 大小                  | 用途                            |
| :--------- | :-------------------- | :------------------------------ |
| CHAR       | 0-255 bytes           | 定长字符串                      |
| VARCHAR    | 0-65535 bytes         | 变长字符串                      |
| TINYBLOB   | 0-255 bytes           | 不超过 255 个字符的二进制字符串 |
| TINYTEXT   | 0-255 bytes           | 短文本字符串                    |
| BLOB       | 0-65 535 bytes        | 二进制形式的长文本数据          |
| TEXT       | 0-65 535 bytes        | 长文本数据                      |
| MEDIUMBLOB | 0-16 777 215 bytes    | 二进制形式的中等长度文本数据    |
| MEDIUMTEXT | 0-16 777 215 bytes    | 中等长度文本数据                |
| LONGBLOB   | 0-4 294 967 295 bytes | 二进制形式的极大文本数据        |
| LONGTEXT   | 0-4 294 967 295 bytes | 极大文本数据                    |



[^1]: 资料来源：[MySQL 数据类型 | 菜鸟教程 (runoob.com)](https://www.runoob.com/mysql/mysql-data-types.html)

------



# [约束](http://c.biancheng.net/view/7576.html#:~:text=%E5%92%8C%E8%BF%90%E7%AE%97%E7%AC%A6-,MySQL%E7%BA%A6%E6%9D%9F%E6%A6%82%E8%BF%B0,-%3C%20%E4%B8%8A%E4%B8%80%E8%8A%82)

```SQL
CREATE TABLE [条件] 表名(
    字段1 数据类型[约束],
    字段2 数据类型[约束],
    ……
    字段3 数据类型[约束]
    )
CONSTRAINT # 可以定义约束名
```
>   #### 码的概念
>
>   >   码：**字段的集合**
>
>   -   表中可以确定实体唯一性的字段的集合叫做**超码**
>   -   能够**确定唯一性的最小的超码**叫做**候选码**
>   -   我们选择出来**用来标识实例的唯一性的候选码**叫做**主键**
>
>   >   例：
>
>   -   学生表：学号、身份证号、姓名、年龄、性别、电话 
>
>   -   超码：{学号} {身份证号} {电话} {学号 姓名} {学号 姓名 年龄}
>
>   -   候选码：{学号} {身份证号}
>
>   -   **主键**：{学号}



## [主键约束](http://c.biancheng.net/view/2440.html#:~:text=MySQL%E4%B8%BB%E9%94%AE%EF%BC%88PRIMARY%20KEY%EF%BC%89)

>   主关键字(primary key)是表中的一个或多个字段，它的值用于唯一地标识表中的某一条记录。
>
>   >   ##### 使用主键应注意以下几点：
>
>   -   每个表只能定义一个主键。
>   -   主键值必须唯一标识表中的每一行，且不能为 NULL，即表中不可能存在有相同主键值的两行数据。这是**唯一性原则**。
>   -   一个字段名只能在联合主键字段表中出现一次。
>   -   联合主键不能包含不必要的多余字段。当把联合主键的某一字段删除后，如果剩下的字段构成的主键仍然满足唯一性原则，那么这个联合主键是不正确的。这是最小化原则。
>
>   ###### 创建联合主键时需要注意以下几点：
>
>   1. 联合主键是由两个或多个列组成的唯一标识符，它们共同决定了表中每行数据的唯一性。
>
>   2. 在创建联合主键时，关键字PRIMARY KEY后面需要跟着所有组成联合主键的列名，并用逗号分隔。
>
>   3. 联合主键的列数和类型应该尽量少而简单，以提高数据库性能和查询效率。通常情况下，不建议使用超过4个列作为联合主键。
>
>   4. 当在其他表中引用具有联合主键的表时，必须使用所有列来定义外键关系。这些列的数据类型和限制约束必须与主键中的对应列相同。
>   5. 与单一主键相比，联合主键的维护和更新比较复杂。当需要在联合主键上进行增删改查操作时，需要考虑到所有列的组合和顺序，以避免数据重复或错误。



```sql
# 设置单字段主键
<字段名> <数据类型> PRIMARY KEY [默认值];

# 在创建表时设置联合主键
CREATE TABLE [条件] 表名(
    字段1 数据类型[约束],
    字段2 数据类型[约束],
    ……
    字段n 数据类型[约束],
    PRIMARY KEY ([字段1，字段2，…,字段n]),
    );
   
# 在修改表时添加主键约束
ALTER TABLE <数据表名> ADD PRIMARY KEY(<字段名>);

# 删除主键约束
ALTER TABLE <数据表名> DROP PRIMARY KEY;
```





## [主键自增长](http://c.biancheng.net/view/7624.html#:~:text=MySQL%20AUTO_INCREMENT%EF%BC%9A-,%E4%B8%BB%E9%94%AE%E8%87%AA%E5%A2%9E%E9%95%BF,-%3C%20%E4%B8%8A%E4%B8%80%E8%8A%82)

[^2]: 详细请阅读：[MySQL AUTO_INCREMENT：主键自增长 (biancheng.net)](http://c.biancheng.net/view/7624.html) 



>   当主键定义为自增长后，这个主键的值就不再需要用户输入数据了，而由数据库系统根据定义自动赋值。每增加一条记录，主键会自动以相同的步长进行增长。
>
>   > - 默认情况下，AUTO_INCREMENT 的初始值是 1，每新增一条记录，字段值自动加 1。
>   > - 一个表中只能有一个字段使用 AUTO_INCREMENT 约束，且该字段必须有唯一索引，以避免序号重复（即为主键或主键的一部分）。
>   > - AUTO_INCREMENT 约束的字段必须具备 NOT NULL 属性。
>   > - AUTO_INCREMENT 约束的字段只能是整数类型（TINYINT、SMALLINT、INT、BIGINT 等）。
>   > - AUTO_INCREMENT 约束字段的最大值受该字段的数据类型约束，如果达到上限，AUTO_INCREMENT 就会失效。

```SQL
# 创建表时设置主键自增长
<字段名> <数据类型> AUTO_INCREMENT
```



## [唯一约束](http://c.biancheng.net/view/2445.html#:~:text=MySQL%E5%94%AF%E4%B8%80%E7%BA%A6%E6%9D%9F%EF%BC%88UNIQUE%20KEY%EF%BC%89)

>   -   唯一约束是指定table的列或列组合不能重复，保证数据的唯一性
>   -   唯一约束不允许出现重复的值，但是可以为多个null
>   -   同一个表可以有多个唯一约束，多个列组合的约束
>   -   如果不给唯一约束名称，就默认和字段相同
>   -   MySQL会给唯一约束的列上默认创建一个唯一索引

>   >   #### 主键（primary key）跟唯一约束（unique）的区别
>
>   -   主键不能为null，唯一约束可以为null（空）
>   -   主键可以作为外键被其他的表引用，唯一约束不可以
>   -   唯一约束的字段在不重复的情况下可以更新，主键很少被改动
>
>   >   ##### 唯一约束与主键约束相似的是它们都可以确保列的唯一性。不同的是，唯一约束在一个表中可有多个，并且设置唯一约束的列允许有空值，但是只能有一个空值。而主键约束在一个表中只能有一个，且不允许有空值。比如，在用户信息表中，为了避免表中用户名重名，可以把用户名设置为唯一约束。

```SQL
# 在创建表时设置唯一约束
<字段名> <数据类型> UNIQUE;

# 在修改表时添加唯一约束
ALTER TABLE <数据表名> ADD CONSTRAINT <唯一约束名> UNIQUE(<字段名>);	
# CONSTRAINT可以定义唯一约束名

# 修改唯一约束
ALTER TABLE <数据表名> MODIFY <数据表名> <数据类型> unique; 

# 删除唯一约束
ALTER TABLE <数据表名> DROP INDEX <唯一约束名>;
```

## [非空约束](http://c.biancheng.net/view/2448.html#:~:text=%E5%92%8C%E8%BF%90%E7%AE%97%E7%AC%A6-,MySQL%E9%9D%9E%E7%A9%BA%E7%BA%A6%E6%9D%9F%EF%BC%88NOT%20NULL%EF%BC%89,-%3C%20%E4%B8%8A%E4%B8%80%E8%8A%82)

>   非空约束（NOT NULL）指字段的值不能为空。对于使用了非空约束的字段，如果用户在添加数据时没有指定值，数据库系统就会报错。可以通过 CREATE TABLE 或 ALTER TABLE 语句实现。在表中某个列的定义后加上关键字 NOT NULL 作为限定词，来约束该列的取值不能为空。
>
>   >   比如，在用户信息表中，如果不添加用户名，那么这条用户信息就是无效的，这时就可以为用户名字段设置非空约束。

```sql
# 在创建表时设置非空约束
<字段名> <数据类型> NOT NULL;

# 在修改表时添加非空约束
ALTER TABLE <数据表名>
CHANGE COLUMN <字段名>
<字段名> <数据类型> NOT NULL;

# 删除非空约束
ALTER TABLE <数据表名>
CHANGE COLUMN <字段名> 
<字段名> <数据类型> NULL;
```

## [默认值约束](http://c.biancheng.net/view/2447.html#:~:text=%E5%92%8C%E8%BF%90%E7%AE%97%E7%AC%A6-,MySQL%E9%BB%98%E8%AE%A4%E5%80%BC%EF%BC%88DEFAULT%EF%BC%89,-%3C%20%E4%B8%8A%E4%B8%80%E8%8A%82)

>   默认值（Default）的完整称呼是“默认值约束（Default Constraint）”，用来指定某列的默认值。在表中插入一条新记录时，如果没有为某个字段
>
>   赋值，系统就会自动为这个字段插入默认值。
>
>   >   例如，员工信息表中，部门位置在北京的较多，那么部门位置就可以默认为“北京”，系统就会自动为这个字段赋值为“北京”。

```SQL
# 在创建表时设置默认值约束
<字段名> <数据类型> DEFAULT <默认值>;
# 其中，“默认值”为该字段设置的默认值，如果是字符类型的，要用单引号括起来。

# 在修改表时添加默认值约束
ALTER TABLE <数据表名>
CHANGE COLUMN <字段名> <数据类型> DEFAULT <默认值>;

# 删除默认值约束
ALTER TABLE <数据表名>
CHANGE COLUMN <字段名> <字段名> <数据类型> DEFAULT NULL;
```

## [检查约束](http://c.biancheng.net/view/2446.html#:~:text=%E5%92%8C%E8%BF%90%E7%AE%97%E7%AC%A6-,MySQL%E6%A3%80%E6%9F%A5%E7%BA%A6%E6%9D%9F%EF%BC%88CHECK%EF%BC%89,-%3C%20%E4%B8%8A%E4%B8%80%E8%8A%82)

>   检查约束（CHECK）是用来检查数据表中字段值有效性的一种手段，可以通过 CREATE TABLE 或 ALTER TABLE 语句实现。设置检查约束时要根据实际情况进行设置，这样能够减少无效数据的输入。
>
>   #### MySQL 8.0之后才支持CHECK约束

```SQL
# 选取设置检查约束的字段
CHECK <表达式>

# 在创建表时设置检查约束
CHECK(<检查约束>)
#示例
CREATE TABLE temp(         
	id INT AUTO_INCREMENT,         
	NAME VARCHAR(20),         
	age INT,         
	PRIMARY KEY(id), 
	CHECK(age > 20) 
	); 

# 在修改表时添加检查约束
ALTER TABLE <数据表名> ADD CONSTRAINT <检查约束名> CHECK(<检查约束>);

# 删除检查约束
ALTER TABLE <数据表名> DROP CONSTRAINT <检查约束名>;
```

## [外键约束](http://c.biancheng.net/view/2441.html#:~:text=MySQL%E5%A4%96%E9%94%AE%E7%BA%A6%E6%9D%9F%EF%BC%88FOREIGN%20KEY%EF%BC%89)

>   外键约束（FOREIGN KEY）是表的一个特殊字段，经常与主键约束一起使用。对于两个具有关联关系的表而言，相关联字段中主键所在的表就是主表（父表），外键所在的表就是从表（子表）。
>
>   -   外键是构建于一个表的两个字段或是两个表的两个字段之间的参照关系
>
>   -   表的外键值必须在主表中能找到或者为空
>
>   -   当主表的记录被从表参照时，主表的记录将不允许删除
>
>   -   如果要删除数据，需要先删除从表中依赖该记录的数据
>   -   **外键的表**叫**从表**，**被引用的表**叫**主表**。
>
>   ###### 定义外键时，需要遵守下列规则：
>
>   -   主表必须已经存在于数据库中，或者是当前正在创建的表。如果是后一种情况，则主表与从表是同一个表，这样的表称为**自参照表**，这种结构称为**自参照完整性**。
>   -   必须为主表定义主键。
>   -   主键不能包含空值，但允许在外键中出现空值。也就是说，只要外键的每个非空值出现在指定的主键中，这个外键的内容就是正确的。
>   -   在主表的表名后面指定字段或字段的组合。这个列或列的组合必须是主表的主键或候选键。
>   -   外键中列的数目必须和主表的主键中列的数目相同。
>   -   外键中列的数据类型必须和主表主键中对应列的数据类型相同。

```SQL
# 在创建表时设置外键约束
[CONSTRAINT <外键名>] FOREIGN KEY(字段名 [，字段名2，…])
REFERENCES <主表名>(主键列1 [，主键列2，…]);
# 示例
CREATE TABLE classinfo3(
	cid VARCHAR(20) PRIMARY KEY,
	NAME VARCHAR(50) UNIQUE
	);

CREATE TABLE IF NOT EXISTS stu(
	s_id VARCHAR(50) PRIMARY KEY,
	s_name VARCHAR(50),
	s_sex CHAR(10) DEFAULT '男',
	cid VARCHAR(20),
	CONSTRAINT FK_cid	
	FOREIGN KEY(cid)
	REFERENCES classinfo3(cid)
	);

# 在修改表时添加外键约束
ALTER TABLE <数据表名> ADD CONSTRAINT <外键名>
FOREIGN KEY(<字段>) REFERENCES <主表名> (<字段>);

# 删除外键约束
ALTER TABLE <表名> DROP FOREIGN KEY <外键约束名>;
```

## 数据完整性

> - 数据的完整性指存储在数据库中的数据应该保持准确性和可靠性。如出现学号相同的数据就是不准确的。
>
> - 数据库采用多种方法来保证数据完整性：外键、约束、触发器。
>
>
> >   #### 完整性分为四大类：
> >
> >   - 实体完整性
> >   - 域完整性
> >   - 参照完整性
> >   - 自定义完整性
> >
> >   ##### 实体完整性、域完整性及参照完整性分别在列、行、表上实施。
>
> 

### 实体完整性

> -   实体完整性是对关系中的记录唯一性。
> -   定义表中的所有行能唯一的标识
> -   表中主属性(字段)不能为Null且不能有相同值
> -   一般用主键、唯一索引、 unique关键字来实现

### 域完整性

>   -   域完整性是对数据表中字段属性的约束
>   -   它是由确定表结构时所定义的字段的属性决定的
>   -   限制数据类型,缺省值,规则,约束,是否可以为空
>   -   域完整性可以确保不会输入无效的值

### 参照完整性

>   -   参照完整性指的就是多表之间的设计,主要使用外键约束。
>   -   多表设计: 一对多、多对多、一对一设计。

### 自定义完整性

>   自定义完整性指针对某一具体[关系数据库](https://baike.baidu.com/item/关系数据库/1237340?fromModule=lemma_inlink)的[约束条件](https://baike.baidu.com/item/约束条件/1046571?fromModule=lemma_inlink)，它反映某一具体应用所涉及的数据必须满足的语义要求。
>
>   例如某个属性必须取唯一值，某个[非主属性](https://baike.baidu.com/item/非主属性/3462646?fromModule=lemma_inlink)也不能取[空值](https://baike.baidu.com/item/空值/6506427?fromModule=lemma_inlink)，某个属性的[取值范围](https://baike.baidu.com/item/取值范围/2770398?fromModule=lemma_inlink)在0-100之间等。



>   # SQL脚本
>
>   >   ## SQL语句基本
>   >
>   >   -   SQL 对大小写不敏感：SELECT 与 select 是相同的。
>   >   -   SQL 语句一条指令的结束必须用“;"来结尾。
>   >   -   符号用英文
>   >
>   >   ### 以下语法中，[ ]中的内容通常为非必要项。
>

# **数据定义语言DDL**

### **CREATE DATABASE** - 创建新数据库

#### 创建数据库 

```SQL
CREATE DATABASE 数据库名;	# 创建数据库
USE 数据库名;	# 使用数据库↓
```

### **CREATE TABLE** - 创建新表

#### 创建数据表

-   创建数据表前先指定使用的数据库，否则无法创建。

```sql
CREATE TABLE 表名(
    字段1 数据类型[约束],
    字段2 数据类型[约束],
    ……
    字段3 数据类型[约束]
    )
    # []:可选内容
    # 最后一条属性不需要逗号。
# --------------------------------------------
# 示例1
CREATE TABLE IF NOT EXISTS student(
    Student_id INT PRIMARY KEY, 	# 为该列设置主键约束来保证值不为空且唯一。
    Student_name VARCHAR(10),
    Student_age TINYINT,
    Student_phone CHAR
    )
```

### SHOW-查看创建

```sql
SHOW CREATE 表名; # 查看表使用的引擎、字符集、核对等相关信息。
```



### DESC（describe）-查看表结构

```sql
DESC 表名;
DESCRIBE 表名;
```

### DROP-表删除

#### 删除表-DROP TABLE  [条件] 表名

```sql
DROP TABLE IF EXISTS 表名;
# ---------------------------
# 示例1：删除学生表
DROP TABLE IF EXISTS student;
# 该操作将表结构跟表中的数据全部删除
```



## ALTER-修改表

>   -   在确定了要修改表之后还要指定要修改表中的哪些元素
>   -   常用到的操作：添加字段，修改字段，删除字段

### 添加字段

#### 添加字段-ALTER TABLE 表名 ADD……

```sql
ALTER TABLE 表名
ADD COLUMN 字段名 数据类型;
# -------------------------------------
# 示例：向学生表里添加学生电话的字段
ALTER TABLE student 
ADD COLUMN student_phone varchar(20);
```

>   **新添加的字段默认添加到最后**，如果需要指定字段的位置可以使用 FIRST | AFTER 关键字

#### 在开头添加字段-ALTER TABLE | FIRST

```SQL
ALTER TABLE 表名
ADD COLUMN 字段名 数据类型 FIRST;
# -------------------------------------
# 示例：向学生表[开头]添加学生电话的字段
ALTER TABLE student 
ADD COLUMN student_phone varchar(20) FIRST;
```

#### 在[指定字段]后添加字段-ALTER TABLE | AFTER

```SQL
ALTER TABLE 表名
ADD COLUMN 字段名 数据类型 
AFTER 指定字段名;
# -------------------------------------
# 示例：在[学生年龄字段后]添加一个字段：学生邮箱
ALTER TABLE student 
ADD COLUMN student_email varchar(20) 
AFTER student_age;
```

### 删除字段

#### ALTER TABLE | DROP

```SQL
ALTER TABLE 表名
DROP COLUMN 字段名;
# -------------------------------------
# 示例：删除一个字段：学生邮箱
ALTER TABLE student 
DROP COLUMN student_email;
```


# **数据操纵语言DML**-增删改

## [INSERT-插入数据(添加数据)](http://c.biancheng.net/view/2574.html#:~:text=MySQL%20INSERT%EF%BC%9A%E6%8F%92%E5%85%A5%E6%95%B0%E6%8D%AE%EF%BC%88%E6%B7%BB%E5%8A%A0%E6%95%B0%E6%8D%AE%EF%BC%89)

>   #### 基本语法
>
>   INSERT 语句有两种语法形式，分别是 **INSERT…VALUES** 语句和 **INSERT…SET** 语句。

### INSERT | VALUES语句

>   #### 基本语法
>
>   ```sql
>   #添加单条数据
>   INSERT INTO <表名>([字段1],[字段2]……[字段n]) VALUES([值1],[值2]……[值n]);
>   
>   #不指定列名时，需要为所有列写入值
>   INSERT INTO <表名> VALUES([值1],[值2]……[值n]);
>   
>   #批量添加数据
>   INSERT INTO <表名>([字段1],[字段2]……[字段n]) VALUES
>   (列值1，列值2，列值3…列值n),
>   (列值a，列值b，列值c…列值n),
>   (列值A，列值B，列值C…列值N);
>   ```

>   ###### 语法说明
>
>   -   `<表名>`：指定被操作的表名。
>   -   `<字段>`：指定需要插入数据的字段。若向表中的所有列插入数据，则全部的字段均可以省略，直接采用 INSERT<表名>VALUES(…) 即可。
>   -   `VALUES` 或 `VALUE` 子句：该子句包含要插入的数据清单。数据清单中数据的顺序要和列的顺序相对应。反之省略字段时，必须向所有列添加数值。
>   -   主键自增列添加值时，可以用空值`NULL`代替，会自动增长。
>
>   #### VALUE 和 VALUES的区别
>
>   `VALUE` 和 `VALUES` 都可以添加数据，区别在于 `VALUES` 可以添加多条（行）数据，也可以添加单条数据，但是 `VALUE` 只能添加单条数据。+
>
>   ##### 所以只需要掌握 VALUES 即可

### INSERT | SELECT 复制

```sql
#使用INSERT实现复制操作。
INSERT INTO <表名>
SELECT * FROM <源表名>
```

## DELETE - 值删除

```SQL
DELETE FROM <表名> [WHERE 子句] [ORDER BY 子句] [LIMIT 子句]
```

>   ###### 语法说明
>
>   -   `<表名>`：指定要删除数据的表名。
>   -   `ORDER BY` 子句：可选项。表示删除时，表中各行将按照子句中指定的顺序进行删除。
>   -   `WHERE` 子句：可选项。表示为删除操作限定删除条件，若省略该子句，则代表删除该表中的所有行。
>   -   `LIMIT` 子句：可选项。用于告知服务器在控制命令被返回到客户端前被删除行的最大值。
>
>   #### 注意：在不使用 WHERE 条件的时候，将删除所有数据。

```sql
#【实例 1】删除 tb_courses_new 表中的全部数据，输入的 SQL 语句和执行结果如下所示。
DELETE FROM tb_courses_new; #不推荐使用，有多少条记录就会执行多少次删除操作。

TRUNCATE TABLE <表名> #推荐使用，先删除表，然后再创建一张一样的表，效率更高。

#【实例 2】在 tb_courses_new 表中，删除 course_id 为 4 的记录，输入的 SQL 语句和执行结果如下所示。
DELETE FROM tb_courses
WHERE course_id=4;
```



## [UPDATE - 修改数据](http://c.biancheng.net/view/2579.html#:~:text=MySQL%20UPDATE%EF%BC%9A%E4%BF%AE%E6%94%B9%E6%95%B0%E6%8D%AE%EF%BC%88%E6%9B%B4%E6%96%B0%E6%95%B0%E6%8D%AE%EF%BC%89)

```sql
UPDATE <表名> SET 字段1=值1 [,字段2=值2… ] [WHERE 子句] [ORDER BY 子句] [LIMIT 子句]
```

>   ###### 语法说明
>
>   -   `<表名>`：用于指定要更新的表名称。
>   -   `SET` 子句：用于指定表中要修改的字段及其列值。其中，每个指定的列值可以是表达式，也可以是该列对应的默认值。如果指定的是默认值，可用关键字 DEFAULT 表示列值。
>   -   [`WHERE`] 子句：可选项。用于限定表中要修改的行。若不指定，则修改表中所有的行。
>   -   [`ORDER BY`] 子句：可选项。用于限定表中的行被修改的次序。
>   -   [`LIMIT`] 子句：可选项。用于限定被修改的行数。
>
>   >   #### 注意：修改一行数据的多个列值时，SET 子句的每个值用逗号分开即可。

# 数据查询语言查

>   我们通过DQL对数据库的表进行查询。你可以查询所有数据，可以查询部分数据，可以分组查询，可以排序等等。对表的查询，也是我们对数据库最常用的操作，也是最复杂的操作。

## [SELECT - 从数据库中查询数据](http://c.biancheng.net/view/2548.html#:~:text=MySQL%20SELECT%EF%BC%9A%E6%95%B0%E6%8D%AE%E8%A1%A8%E6%9F%A5%E8%AF%A2%E8%AF%AD%E5%8F%A5)

### 查询基础

```sql
SELECT
{* | <字段列名>}
[
FROM <表 1>, <表 2>…
[WHERE <表达式>
[GROUP BY <group by definition>
[HAVING <expression> [{<operator> <expression>}…]]
[ORDER BY <order by definition>]
[LIMIT[<offset>,] <row count>]
]
```

>   ###### 其中，各条子句的含义如下：
>
>   -   `{*|<字段列名>}`包含星号通配符的字段列表，表示所要查询字段的名称。
>   -   `<表 1>，<表 2>…`，表 1 和表 2 表示查询数据的来源，可以是单个或多个。
>   -   `WHERE <表达式>`是可选项，如果选择该项，将限定查询数据必须满足该查询条件。
>   -   `GROUP BY< 字段 >`，该子句告诉 MySQL 如何显示查询出来的数据，并按照指定的字段分组。
>   -   `[ORDER BY< 字段 >]`，该子句告诉 MySQL 按什么样的顺序显示查询出来的数据，可以进行的排序有升序（ASC）和降序（DESC），默认情况下是升序。
>   -   `[LIMIT[<offset>，]<row count>]`，该子句告诉 MySQL 每次显示查询出来的数据条数，必须放在最后，其他的子句则没有顺序限制。

```sql
#查看表所有内容
SELECT * FROM 表名;
#查看表内指定列内容
SELECT <列名> FROM <表名>;
```

### 去重查询 | DISTINCT

```SQL
SELECT DISTINCT <字段名> FROM <表名>;
```

>   ###### 注意事项
>
>   -   DISTINCT 关键字只能在 SELECT 语句中使用。
>   -   在对一个或多个字段去重时，DISTINCT 关键字必须在所有字段的最前面。
>   -   如果 DISTINCT 关键字后有多个字段，则会对多个字段进行组合去重，也就是说，只有多个字段组合起来完全是一样的情况下才会被去重。

### 使用 INSERT | SELECT 实现复制操作

```sql
INSERT INTO <表名>
SELECT * FROM <源表名>;
```

### 表数据复制

```sql
CREATE TABLE <新表名> AS
SELECT <字段名|*> FROM <源表名>;

RENAME TABLE <新表名1> TO <旧表名1>,<新表名2> TO <旧表名2>……; #重命名表的方法
```

>   ###### 注意事项
>
>   这种方式只复制数据，约束跟索引都不会被复制。

## WHERE | 带条件查询

>   ###### 查询条件可以是：
>
>   -   带比较运算符和逻辑运算符的查询条件
>   -   带 BETWEEN AND 关键字的查询条件
>   -   带 IS NULL 关键字的查询条件
>   -   带 IN 关键字的查询条件
>   -   带 LIKE 关键字的查询条件

```SQL
SELECT 列,列…. FROM 表名 
[WHERE 条件 ]
```

### IN | NOT IN

```SQL
#查询地址在泰安 或者 济南的老师信息
SELECT * FROM teacher WHERE address IN( '济南' ,'泰安');
```

## [聚合函数](http://c.biancheng.net/mysql/function/#:~:text=%E5%B7%A5%E4%BD%9C%E6%97%A5%E7%B4%A2%E5%BC%95-,MySQL%20%E8%81%9A%E5%90%88%E5%87%BD%E6%95%B0,-%E5%87%BD%E6%95%B0%E5%90%8D%E7%A7%B0)

>   聚合函数是对一组值执行计算并返回单一结果的函数，常配合GROUP BY语法一起使用。
>
>   -   我们可以认为一张表本身就是一个组。
>
>   -   如果没有GROUP BY的分组约束，聚合最终生成一条记录。
>
>   -   如果查询中同时存在聚合跟未聚合的字段，未聚合的字段只截留第一条记录中的值
>
>   ###### 注意事项
>
>   1、聚合函数不能当做WHERE 从句的判断条件，因为WHERE从句要先于聚合函数执行。可以使用子查询达到想要的效果。
>
>   ```SQL
>   SELECT t_name FROM teacher WHERE t_salary = AVG(t_salary)；  #语法错误
>   ```
>
>   2、聚合函数不能嵌套聚合函数。
>
>   ```SQL
>   SELECT AVG(MIN(t_salary) FROM teacher; #语法错误
>   ```

| 函数名称                                         | 作用                             |
| ------------------------------------------------ | -------------------------------- |
| [MAX](http://c.biancheng.net/mysql/max.html)     | 查询指定列的最大值               |
| [MIN](http://c.biancheng.net/mysql/min.html)     | 查询指定列的最小值               |
| [COUNT](http://c.biancheng.net/mysql/count.html) | 统计查询结果的行数               |
| [SUM](http://c.biancheng.net/mysql/sum.html)     | 求和，返回指定列的总和           |
| [AVG](http://c.biancheng.net/mysql/avg.html)     | 求平均值，返回指定列数据的平均值 |

### COUNT

>   COUNT() 函数统计数据表中包含的记录行的总数，或者根据查询结果返回列中包含的数据行数，使用方法有以下两种： 
>
>   -   COUNT(*) 计算表中总的行数，无论某列有数值或者为空值。
>   -   COUNT（字段名）计算指定列下总的行数，计算时将忽略空值的行。
>
>   ![image-20230531095739105](./Mysql%20%E6%95%B0%E6%8D%AE%E5%BA%93.assets/image-20230531095739105.png)

>   带条件的查询
>
>
>   ```sql
>   \#查询地址在济南的老师有多少个
>   SELECT COUNT(*) FROM teacher  WHERE address = '济南';
>   ```

>   集合函数可以使用DISTINCT去重复
>
>     ```sql
>\#查询老师的地区分布（重复的地区只统计一次）
>   SELECT COUNT(DISTINCT(t_address)) FROM teacher;
>     ```
>   

### MIN | MAX

#### MIN

>    MIN() 函数是用来返回查询列中的最小值。

```sql
#返回最少的工资是多少 
SELECT MIN(t_salary) FROM teacher; #返回 "teacher" 表中的最低工资值作为结果。
```

#### MAX

>   MAX() 函数是用来返回指定列中的最大值。

```SQL
#返回 "teacher" 表中的最高工资值作为结果。
SELECT MAX(t_salary) FROM teacher;
```

>   一个查询中可以有**多个聚合字段**
>
>   ```sql
>   SELECT MIN(t_salary),MAX(t_salary) FROM teacher;
>   ```

### AVG

>   AVG() 函数通过计算返回的行数和每一行数据的和，求得指定列数据的平均值。

```sql
#求工资的平均值
SELECT AVG(t_salary) FROM teacher;
```

>   聚合函数不会计算NULL值的字段，如果需要将NULL值的字段一并聚合运算需要将NULL转换成可运算的值
>
>   ```SQL
>   SELECT AVG(IFNULL(t_salary,0)), FROM teacher;
>   ```

### SUM

>   SUM() 是一个求总和的函数，返回指定列值的总和。
>
>   ###### SUM() 函数是如何工作的？
>
>   -   如果在没有返回匹配行 SELECT 语句中使用 SUM 函数，则 SUM 函数返回 NULL，而不是 0。
>   -   DISTINCT 运算符允许计算集合中的不同值。
>   -   SUM 函数忽略计算中的 NULL 值。

```SQL
# 返回工资总和
SELECT SUM(t_salary) FROM teacher;
```

## 空值和常量列

### 空值和空字符串

>   -   在MySQL数据库中字段的空值null和空字符串是不一样的。
>
>   -   在MySQL中null值需要使用IS NULL 和 IS NOT NULL 语法来查询。
>       -   不能使用 `<字段名> = null`。

### 常量列的使用

>   -   在MySQL中可以在查询结果中放入一些常量。
>
>   -   字符串用引号括起来，数值不需要。
>
>   ```sql
>   SELECT 列1,列2,…'常量'  FROM  表名;
>   ```
>
>   ![image-20230523231927106](./Mysql%20%E6%95%B0%E6%8D%AE%E5%BA%93.assets/image-20230523231927106.png)

## 别名的使用

>   >   表的字段名一般都以英文命名。而我有时候统计查询结果时把表头改成汉字比较直观，这就用到了别名的语法。别名分为字段别名、表别名。
>
>   ```sql
>   SELECT <字段名1> AS <别名1>,<字段名2> AS <别名2>,……  FROM  <表名>  AS <表别名>;
>   ```
>
>   -   `AS`关键字可以省略，省略后需要将表名和别名用空格隔开。
>
>   ![image-20230523232332579](./Mysql%20%E6%95%B0%E6%8D%AE%E5%BA%93.assets/image-20230523232332579.png)
>
>   ![image-20230523233001676](./Mysql%20%E6%95%B0%E6%8D%AE%E5%BA%93.assets/image-20230523233001676.png)

>   ###### 表名的作用
>
>   -   简化书写：比较长的表或者较多的表使用别名比较方便
>   -   结果易懂：让比较晦涩的字段名称显示为通俗易懂的字段名称
>   -   很多工具中使用别名可以很好的发挥代码提示功能

## [行数限定和排序](http://c.biancheng.net/view/7389.html#:~:text=MySQL%20LIMIT%EF%BC%9A%E9%99%90%E5%88%B6%E6%9F%A5%E8%AF%A2%E7%BB%93%E6%9E%9C%E7%9A%84%E6%9D%A1%E6%95%B0)

### 行数限定

>   LIMIT 是 MySQL 中的一个特殊关键字，用于指定查询结果从哪条记录开始显示，一共显示多少条记录。
>
>   LIMIT 关键字有 3 种使用方式，即指定初始位置、不指定初始位置以及与 OFFSET 组合使用。

>   ```SQL
>   SELECT  <字段名1>,<字段名2>……  FROM  <表名>   LIMIT  [start] nums
>   ```
>
>   -   `start`：从第几行开始，可选，不写的话从0开始
>   -   `nums`：总共要查询几行
>   -   不指定起始`start`行时，查询前 `nums` 行
>   -   在MySQL中，行数从0开始往下计算。
>
>   ###### LIMIT 后的两个参数必须都是正整数。

### 排序

>   MySQL中可以通过ORDER BY 语法对查询的结果集进行排序。
>
>   ```sql
>   ORDER BY <字段名> [ASC|DESC]
>   ```
>
>   ###### 语法说明如下：
>
>   -   字段名：表示需要排序的字段名称，多个字段时用逗号隔开。
>   -   ASC|DESC：`ASC`表示字段按升序排序；`DESC`表示字段按降序排序。其中`ASC`为默认值。
>   -   ASC表示Ascending，意思是升序的；而DESC则表示Descending，意思是降序的。
>
>   ###### 使用 ORDER BY 关键字应该注意以下几个方面：
>
>   -   ORDER BY 关键字后可以跟子查询。
>   -   当排序的字段中存在空值时，ORDER BY 会将该空值作为最小值来对待。
>   -   ORDER BY 指定多个字段进行排序时，MySQL 会按照字段的顺序从左到右依次进行排序。
>
>   ###### 示例
>
>   ```sql
>   SELECT * FROM teacher ORDER BY salary ASC;
>   ```
>
>   

## [分组查询](http://c.biancheng.net/view/7408.html#:~:text=%E8%A1%A8%E4%B8%AD%E6%95%B0%E6%8D%AE-,MySQL%E4%BD%BF%E7%94%A8GROUP%20BY%E5%88%86%E7%BB%84%E6%9F%A5%E8%AF%A2,-%3C%20%E4%B8%8A%E4%B8%80%E8%8A%82)

>   GROUP BY可以对一张表自定义的分成若干组，这样就可以分组统计数据。
>
>   ```SQL
>   SELECT … FROM 表名 WHERE 条件  GROUP BY 字段1[,字段2,字段3];
>   ```

>   -   分组字段的先后顺序决定了分组的主次
>   -   后分组的字段将在先分组中继续分组
>   -   对应的参与分组的字段的值都相等的记录才会归为一组

>   -   ORDER BY 是对GROUP BY分组的字段进行排序
>   -   如果分组的字段跟排序的字段相同，ORDER BY可以省略

### GROUP BY 与 GROUP_CONCAT()

>   GROUP BY 关键字可以和 GROUP_CONCAT() 函数一起使用。GROUP_CONCAT() 函数会把每个分组的字段值都显示出来。

```SQL
SELECT `sex`, GROUP_CONCAT(name) FROM tb_students_info 
    -> GROUP BY sex;
+------+----------------------------+
| sex  | GROUP_CONCAT(name)         |
+------+----------------------------+
| 女   | Henry,Jim,John,Thomas,Tom  |
| 男   | Dany,Green,Jane,Lily,Susan |
+------+----------------------------+
#由结果可以看到，查询结果分为两组，sex 字段值为“女”的是一组，值为“男”的是一组，且每组的学生姓名都显示出来了。
```

### GROUP BY 与聚合函数

>   在数据统计时，GROUP BY 关键字经常和聚合函数一起使用。
>
>   聚合函数包括 COUNT()，SUM()，AVG()，MAX() 和 MIN()。其中，COUNT() 用来统计记录的条数；SUM() 用来计算字段值的总和；AVG() 用来计算字段值的平均值；MAX() 用来查询字段的最大值；MIN() 用来查询字段的最小值。

>   下面根据 tb_students_info 表的 sex 字段进行分组查询，使用 COUNT() 函数计算每一组的记录数。SQL 语句和运行结果如下：
>
>   ```SQL
>   mysql> SELECT sex,COUNT(sex) FROM tb_students_info 
>       -> GROUP BY sex;
>   +------+------------+
>   | sex  | COUNT(sex) |
>   +------+------------+
>   | 女   |          5 |
>   | 男   |          5 |
>   +------+------------+
>   2 rows in set (0.00 sec)
>   ```
>
>   结果显示，sex 字段值为“女”的记录是一组，有 5 条记录；sex 字段值为“男”的记录是一组，有 5 条记录。

### GROUP BY 与 WITH ROLLUP

>   WITH POLLUP 关键字用来在所有记录的最后加上一条记录，这条记录是上面所有记录的总和，即统计记录数量。

>   下面根据 tb_students_info 表中的 sex 字段进行分组查询，并使用 WITH ROLLUP 显示记录的总和。
>
>   ```SQL
>   mysql> SELECT sex,GROUP_CONCAT(name) FROM tb_students_info 
>       ->GROUP BY sex WITH ROLLUP;
>   +------+------------------------------------------------------+
>   | sex  | GROUP_CONCAT(name)                                   |
>   +------+------------------------------------------------------+
>   | 女   | Henry,Jim,John,Thomas,Tom                            |
>   | 男   | Dany,Green,Jane,Lily,Susan                           |
>   | NULL | Henry,Jim,John,Thomas,Tom,Dany,Green,Jane,Lily,Susan |
>   +------+------------------------------------------------------+
>   3 rows in set (0.00 sec)
>   ```
>
>   查询结果显示，GROUP_CONCAT(name) 显示了每个分组的 name 字段值。同时，最后一条记录的 GROUP_CONCAT(name) 字段的值刚好是上面分组 name 字段值的总和。

## [过滤分组-HAVING](http://c.biancheng.net/view/7416.html#:~:text=MySQL%20HAVING%EF%BC%9A-,%E8%BF%87%E6%BB%A4%E5%88%86%E7%BB%84,-%3C%20%E4%B8%8A%E4%B8%80%E8%8A%82)

>   在 MySQL 中，可以使用 HAVING 关键字对分组后的数据进行过滤。
>
>   >   使用 HAVING 关键字的语法格式如下：
>   >
>   >   ```SQL
>   >   HAVING <查询条件>
>   >   ```
>
>   HAVING 关键字和 WHERE 关键字都可以用来过滤数据，且 HAVING 支持 WHERE 关键字中所有的操作符和语法。
>
>   ###### 但是 WHERE 和 HAVING 关键字也存在以下几点差异：
>
>   -   一般情况下，WHERE 用于过滤数据行，而 HAVING 用于过滤分组。
>   -   WHERE 查询条件中不可以使用聚合函数，而 HAVING 查询条件中可以使用聚合函数。
>   -   WHERE 在数据分组前进行过滤，而 HAVING 在数据分组后进行过滤 。
>   -   WHERE 针对数据库文件进行过滤，而 HAVING 针对查询结果进行过滤。也就是说，WHERE 根据数据表中的字段直接进行过滤，而 HAVING 是根据前面已经查询出的字段进行过滤。
>   -   WHERE 查询条件中不可以使用字段别名，而 HAVING 查询条件中可以使用字段别名。

>   查询部门人数大于2的部门：
>
>   如果使用WHERE，则需要使用子查询来达到效果
>
>   ```SQL
>   SELECT * FROM (
>   	SELECT dep_id,COUNT(1) c FROM teacher GROUP BY dep_id
>   ) tmp WHERE c>2;
>   ```
>
>   如果使用HAVING，则会简单很多
>
>   ```SQL
>   SELECT dep_id,COUNT(1) c FROM teacher GROUP BY dep_id HAVING COUNT(1)>2;
>   ```

```sql
#编写顺序
SELECT … FROM … WHERE … GROUP BY … HAVING … ORDER BY
#执行顺序：
WHERE -> GROUP BY -> HAVING -> SELECT -> ORDER BY 
```

## 连接查询

### 内连接

>   内连接使用在FROM子句中的两个或多个表，通过列之间的匹配来获取满足条件的行。连接条件在ON子句中指定，指定连接的列应该相等。内连接只返回符合连接条件的匹配行。

```SQL
SELECT 列名
FROM 表1
INNER JOIN 表2 ON 表1.列名 = 表2.列名;
```

#### 隐式内连接

>   隐式内连接的结果是两个表中匹配的行的组合，不匹配的行将被排除在结果之外。
>
>   需要注意的是，隐式内连接的语法相对简洁，但可读性较低，并且不够明确，容易造成语义歧义。因此，显式内连接（使用INNER JOIN）通常更推荐使用，以提高查询的可读性和可维护性。

```SQL
SELECT 列名
FROM 表1, 表2
WHERE 表1.列名 = 表2.列名;
```

#### 自连接

>   自连接是指在一个表内部进行连接操作，将同一个表视为两个独立的实例，并通过列之间的匹配来获取满足条件的行。
>
>   自连接的结果是根据连接条件从同一表中获取的满足条件的行。
>
>   自连接常用于需要比较同一表中的不同行之间的关系的情况，例如在具有层级结构的表中查找父子关系。

```SQL
SELECT 列名
FROM 表名 AS t1, 表名 AS t2
WHERE t1.列名 = t2.列名;
```

### 外连接

>   外连接（Outer Join）是一种连接操作，它可以返回不仅匹配的行，还包括未匹配的行。外连接分为左连接（Left Join）和右连接（Right Join）。

#### 左连接

>   左连接返回左表中的所有行，以及与右表中匹配的行。如果右表中没有匹配的行，则返回NULL值。

```sql
SELECT 列名
FROM 左表
LEFT JOIN 右表 ON 左表.列名 = 右表.列名;
```

>   ###### 示例
>
>   ```sql
>   SELECT t.te_name, d.dep_name
>   FROM teacher t
>   LEFT JOIN departmentinfo d ON t.dep_id = d.dep_id;
>   ```
>
>   这个示例使用左连接将"teacher"表和"departmentinfo"表连接起来。左连接返回左表中的所有行，以及与右表中匹配的行。如果右表中没有匹配的行，则返回NULL值。这个查询目的是获取每位教师的姓名（te_name）以及所属部门的名称（dep_name）。
>
>   输出结果：输出结果将包括"teacher"表中的所有行，对于每一行，如果有匹配的部门信息，则返回对应的部门名称，否则部门名称列将包含NULL值。

#### 右连接

>   右连接返回右表中的所有行，以及与左表中匹配的行。如果左表中没有匹配的行，则返回NULL值。

```sql
SELECT 列名
FROM 左表
RIGHT JOIN 右表 ON 左表.列名 = 右表.列名;
```

>   ###### 示例
>
>   ```SQL
>   SELECT t.te_name, d.dep_name
>   FROM teacher t
>   RIGHT JOIN departmentinfo d ON t.dep_id = d.dep_id;
>   ```
>
>   这个示例使用右连接将"teacher"表和"departmentinfo"表连接起来。右连接返回右表中的所有行，以及与左表中匹配的行。如果左表中没有匹配的行，则返回NULL值。这个查询目的是获取每个部门的名称（dep_name）以及属于该部门的教师的姓名（te_name）。
>
>   输出结果：输出结果将包括"departmentinfo"表中的所有行，对于每一行，如果有匹配的教师信息，则返回对应的教师姓名，否则教师姓名列将包含NULL值。

>   ##### ChatGPT的回答
>
>   在关系型数据库中，连接（Join）是用于将两个或多个表根据共同的列值进行关联的操作。连接操作有多种类型，包括内连接（Inner Join）、外连接（Outer Join）、左连接（Left Join）和右连接（Right Join）。下面我会为您解释每种连接类型的含义和用法：
>
>   >   1.  内连接（Inner Join）： 内连接是最常用的连接类型之一。它通过匹配两个表中的共同列值，返回两个表中满足连接条件的行的组合。只有在两个表中共有的列值匹配时，才会返回结果。内连接可以通过在查询中使用关键字 INNER JOIN 或省略关键字 INNER JOIN 而直接指定连接条件来实现。
>   >   2.  外连接（Outer Join）： 外连接用于返回匹配和不匹配的行，包括左外连接和右外连接。外连接中的表被称为主表，而另一个表被称为从表。外连接允许在连接条件不满足时，仍然返回主表中的所有行。
>   >       1.  左连接（Left Join）： 左连接是一种外连接类型，它返回左表中的所有行以及满足连接条件的右表中的匹配行。如果连接条件不满足，右表的列值将为 NULL。
>   >       2.  右连接（Right Join）： 右连接是一种外连接类型，与左连接相反。它返回右表中的所有行以及满足连接条件的左表中的匹配行。如果连接条件不满足，左表的列值将为 NULL。
>
>   ###### 下面是一个简单的示例来说明连接的不同类型：
>
>   ##### 假设我们有两个表，一个是 "Customers" 表，包含客户信息，另一个是 "Orders" 表，包含订单信息。我们想要根据客户的ID将两个表连接起来，获取每个客户以及他们的订单信息。
>
>   >   -   内连接示例： 
>   >
>   >       ```SQL
>   >       SELECT Customers.CustomerID, Customers.CustomerName, Orders.OrderID FROM Customers INNER JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
>   >       ```
>   >
>   >   这个查询将返回所有在 "Customers" 表和 "Orders" 表中具有匹配 CustomerID 的行。
>
>   >   -   左连接示例： 
>   >
>   >       ```SQL
>   >       SELECT Customers.CustomerID, Customers.CustomerName, Orders.OrderID FROM Customers LEFT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
>   >       ```
>   >
>   >   这个查询将返回所有在 "Customers" 表中的行，以及与之匹配的 "Orders" 表中的行。如果某个客户没有对应的订单，相关的 OrderID 列值将为 NULL。
>
>   >   -   右连接示例： 
>   >
>   >       ```SQL
>   >       SELECT Customers.CustomerID, Customers.CustomerName, Orders.OrderID FROM Customers RIGHT JOIN Orders ON Customers.CustomerID = Orders.CustomerID;
>   >       ```
>   >
>   >   这个查询将返回所有在 "Orders" 表中的行，以及与之匹配的 "Customers" 表中的行。如果某个订单没有对应的客户，相关的 CustomerID 和 CustomerName 列值将为 NULL。
>
>   这些是连接的基本概念和用法，您可以根据实际需求选择适当的连接类型来获取所需的数据。



## 子查询

>   子查询是一个嵌套在主查询内部的查询语句。
>
>   子查询是 MySQL 中比较常用的查询方法，通过子查询可以实现多表查询。子查询指将一个查询语句嵌套在另一个查询语句中。子查询可以在 SELECT、UPDATE 和 DELETE 语句中使用，而且可以进行多层嵌套。在实际开发时，子查询经常出现在 WHERE 子句中。
>
>   >   1.  查询的结果如果是一行一列，可以将结果看成一个值来使用
>   >   2.  查询的结果是多列、多行、多行多列，可以看成一个临时表来使用

>   ###### 查询的结果如果是一行一列，可以将结果看成一个值来使用
>
>   ```SQL
>   #查询工资最高的老师信息
>   SELECT * FROM teacher
>   WHERE te_salary = (SELECT MAX(te_salary) FROM teacher);
>   ```

>   ###### 查询的结果是多列、多行、多行多列，可以看成一个临时表来使用
>
>   ```SQL
>   #查询跟张明老师在同一个地址的老师信息（不包括张明）
>   SELECT * FROM (
>   	SELECT * FROM teacher WHERE te_address IN (
>   		SELECT te_address FROM teacher WHERE te_name = '张明')
>   	) AS b WHERE b.te_name <> '张明';
>   ```



## [模糊查询](http://c.biancheng.net/view/7395.html#:~:text=MySQL%20LIKE%EF%BC%9A-,%E6%A8%A1%E7%B3%8A%E6%9F%A5%E8%AF%A2,-%3C%20%E4%B8%8A%E4%B8%80%E8%8A%82)

>   ###### 通配符的分类
>
>   1.  "%" 百分号通配符: 表示任何字符出现任意次数 (可以是0次)。
>   2.  "_" 下划线通配符:表示只能匹配单个字符,不能多也不能少,就是一个字符。当然，也可以like "陈____"，数量不限。
>   3.  like操作符:LIKE作用是指示mysql后面的搜索模式是利用通配符而不是直接相等匹配进行比较；但如果like后面没出现通配符，则在SQL执行优化时将 like 默认为 “=”执行
>
>   ```SQL
>   SELECT <列名> from <表名> where <字段名> like '%_';
>   #示例
>   SELECT * from app_info where appName like '%网%';
>   ```
>
>   

# [常用函数](http://c.biancheng.net/mysql/function/#:~:text=MySQL%E5%87%BD%E6%95%B0%E5%A4%A7%E5%85%A8%EF%BC%8CMySQL%E5%B8%B8%E7%94%A8%E5%87%BD%E6%95%B0%E6%B1%87%E6%80%BB)

>   •在java中String类型的数据已经封装好了求字符串长度的方法
>
>   •在MySQL中同样封装一些很实用的方法供我们使用
>
>   ###### MySQL中函数主要分为四大类
>
>   1.  字符串函数
>   2.  数学函数
>   3.  日期时间函数
>   4.  控制流函数（流程控制函数）

### [字符串函数](http://c.biancheng.net/mysql/function/#:~:text=%E4%BD%99%E5%88%87%E5%80%BC-,MySQL%20%E5%AD%97%E7%AC%A6%E4%B8%B2%E5%87%BD%E6%95%B0,-%E5%87%BD%E6%95%B0%E5%90%8D%E7%A7%B0)

>   | 函数                                                     | 作用                                                         |
>   | -------------------------------------------------------- | ------------------------------------------------------------ |
>   | [LENGTH](http://c.biancheng.net/mysql/length.html)       | 计算字符串长度函数，返回字符串的字节长度                     |
>   | CHAR_LENGTH                                              | 可以返回字符串的字符长度                                     |
>   | TRIM                                                     | 去掉字符串两边的空格                                         |
>   | [INSERT](http://c.biancheng.net/mysql/insert.html)       | 替换字符串函数                                               |
>   | MID                                                      | 可以从某个位置获取某个长度的字符（不是字节）                 |
>   | [CONCAT](http://c.biancheng.net/mysql/concat.html)       | 合并字符串函数，返回结果为连接参数产生的字符串，参数可以使一个或多个 |
>   | [LOWER](http://c.biancheng.net/mysql/lower.html)         | 将字符串中的字母转换为小写                                   |
>   | [UPPER](http://c.biancheng.net/mysql/upper.html)         | 将字符串中的字母转换为大写                                   |
>   | [LEFT](http://c.biancheng.net/mysql/left.html)           | 从左侧字截取符串，返回字符串左边的若干个字符                 |
>   | [RIGHT](http://c.biancheng.net/mysql/right.html)         | 从右侧字截取符串，返回字符串右边的若干个字符                 |
>   | [TRIM](http://c.biancheng.net/mysql/trim.html)           | 删除字符串左右两侧的空格                                     |
>   | [REPLACE](http://c.biancheng.net/mysql/replace.html)     | 字符串替换函数，返回替换后的新字符串                         |
>   | [SUBSTRING](http://c.biancheng.net/mysql/substring.html) | 截取字符串，返回从指定位置开始的指定长度的字符换             |
>   | [REVERSE](http://c.biancheng.net/mysql/reverse.html)     | 字符串反转（逆序）函数，返回与原始字符串顺序相反的字符串     |
>

#### LENGTH 函数

>   LENGTH(str) 函数的返回值为字符串的字节长度，使用 uft8（UNICODE 的一种变长字符编码，又称万国码）编码字符集时，一个汉字是 3 个字节，一个数字或字母是一个字节。

```sql
 SELECT LENGTH('name'),LENGTH('数据库')……
```

#### CHAR_LENGTH 函数

>   CHAR_LENGTH(str) 函数的返回值为字符串的字符长度，使用 uft8（UNICODE 的一种变长字符编码，又称万国码）编码字符集时，一个汉字是 2个字符，一个数字或字母是一个字符。

```sql
 SELECT CHAR_LENGTH('name'),CHAR_LENGTH('数据库')……
```



### [数学函数](http://c.biancheng.net/mysql/function/#:~:text=%E8%81%9A%E5%90%88%E5%87%BD%E6%95%B0%E7%AD%89%E3%80%82-,MySQL%20%E6%95%B0%E5%80%BC%E5%9E%8B%E5%87%BD%E6%95%B0,-%E5%87%BD%E6%95%B0%E5%90%8D%E7%A7%B0)

>   | 函数                                                         | 作用                                                       |
>   | ------------------------------------------------------------ | ---------------------------------------------------------- |
>   |                                                              |                                                            |
>   |                                                              |                                                            |
>   |                                                              |                                                            |
>   |                                                              |                                                            |
>   | UUID                                                         | 生成唯一的设备标识符（属于功能性函数）                     |
>   | LEAST                                                        | 可以求取最小的数字                                         |
>   | GREATEST                                                     | 可以求取最大的数字                                         |
>   |                                                              |                                                            |
>   | [ABS](http://c.biancheng.net/mysql/abc.html)                 | 求绝对值                                                   |
>   | [SQRT](http://c.biancheng.net/mysql/sqrt.html)               | 求二次方根                                                 |
>   | [MOD](http://c.biancheng.net/mysql/mod.html)                 | 求余数                                                     |
>   | [CEIL 和 CEILING](http://c.biancheng.net/mysql/ceil_celing.html) | 两个函数功能相同，都是返回不小于参数的最小整数，即向上取整 |
>   | [FLOOR](http://c.biancheng.net/mysql/floor.html)             | 向下取整，返回值转化为一个BIGINT                           |
>   | [RAND](http://c.biancheng.net/mysql/rand.html)               | 生成一个0~1之间的随机数，传入整数参数是，用来产生重复序列  |
>   | [ROUND](http://c.biancheng.net/mysql/round.html)             | 对所传参数进行四舍五入                                     |
>   | [SIGN](http://c.biancheng.net/mysql/sign.html)               | 返回参数的符号                                             |
>   | [POW 和 POWER](http://c.biancheng.net/mysql/pow_power.html)  | 两个函数的功能相同，都是所传参数的次方的结果值             |
>   | [SIN](http://c.biancheng.net/mysql/sin.html)                 | 求正弦值                                                   |
>   | [ASIN](http://c.biancheng.net/mysql/asin.html)               | 求反正弦值，与函数 SIN 互为反函数                          |
>   | [COS](http://c.biancheng.net/mysql/cos.html)                 | 求余弦值                                                   |
>   | [ACOS](http://c.biancheng.net/mysql/acos.html)               | 求反余弦值，与函数 COS 互为反函数                          |
>   | [TAN](http://c.biancheng.net/mysql/tan.html)                 | 求正切值                                                   |
>   | [ATAN](http://c.biancheng.net/mysql/atan.html)               | 求反正切值，与函数 TAN 互为反函数                          |
>   | [COT](http://c.biancheng.net/mysql/cot.html)                 | 求余切值                                                   |
>   |                                                              |                                                            |
>   |                                                              |                                                            |
>   |                                                              |                                                            |
>   |                                                              |                                                            |
>   |                                                              |                                                            |
>   |                                                              |                                                            |
>   |                                                              |                                                            |
>

### [日期时间函数](http://c.biancheng.net/mysql/function/#:~:text=%E7%9A%84%E5%AD%97%E7%AC%A6%E4%B8%B2-,MySQL%20%E6%97%A5%E6%9C%9F%E5%92%8C%E6%97%B6%E9%97%B4%E5%87%BD%E6%95%B0,-%E5%87%BD%E6%95%B0%E5%90%8D%E7%A7%B0)

>   | 函数名称                                                     | 作 用                                                        |
>   | ------------------------------------------------------------ | ------------------------------------------------------------ |
>   | [CURDATE 和 CURRENT_DATE](http://c.biancheng.net/mysql/curdate_current_date.html) | 两个函数作用相同，返回当前系统的日期值                       |
>   | [CURTIME 和 CURRENT_TIME](http://c.biancheng.net/mysql/curtime_current_time.html) | 两个函数作用相同，返回当前系统的时间值                       |
>   | [NOW 和 SYSDATE](http://c.biancheng.net/mysql/now_sysdate.html) | 两个函数作用相同，返回当前系统的日期和时间值                 |
>   | [UNIX_TIMESTAMP](http://c.biancheng.net/mysql/unix_timestamp.html) | 获取UNIX时间戳函数，返回一个以 UNIX 时间戳为基础的无符号整数 |
>   | [FROM_UNIXTIME](http://c.biancheng.net/mysql/from_unixtime.html) | 将 UNIX 时间戳转换为时间格式，与UNIX_TIMESTAMP互为反函数     |
>   | [MONTH](http://c.biancheng.net/mysql/month.html)             | 获取指定日期中的月份                                         |
>   | [MONTHNAME](http://c.biancheng.net/mysql/monthname.html)     | 获取指定日期中的月份英文名称                                 |
>   | [DAYNAME](http://c.biancheng.net/mysql/dayname.html)         | 获取指定曰期对应的星期几的英文名称                           |
>   | [DAYOFWEEK](http://c.biancheng.net/mysql/dayofweek.html)     | 获取指定日期对应的一周的索引位置值                           |
>   | [WEEK](http://c.biancheng.net/mysql/week.html)               | 获取指定日期是一年中的第几周，返回值的范围是否为 0〜52 或 1〜53 |
>   | [DAYOFYEAR](http://c.biancheng.net/mysql/dayofyear.html)     | 获取指定曰期是一年中的第几天，返回值范围是1~366              |
>   | [DAYOFMONTH](http://c.biancheng.net/mysql/dayofmonth.html)   | 获取指定日期是一个月中是第几天，返回值范围是1~31             |
>   | [YEAR](http://c.biancheng.net/mysql/year.html)               | 获取年份，返回值范围是 1970〜2069                            |
>   | [TIME_TO_SEC](http://c.biancheng.net/mysql/time_to_sec.html) | 将时间参数转换为秒数                                         |
>   | [SEC_TO_TIME](http://c.biancheng.net/mysql/sec_to_time.html) | 将秒数转换为时间，与TIME_TO_SEC 互为反函数                   |
>   | [DATE_ADD 和 ADDDATE](http://c.biancheng.net/mysql/date_add_adddate.html) | 两个函数功能相同，都是向日期添加指定的时间间隔               |
>   | [DATE_SUB 和 SUBDATE](http://c.biancheng.net/mysql/date_sub_subdate.html) | 两个函数功能相同，都是向日期减去指定的时间间隔               |
>   | [ADDTIME](http://c.biancheng.net/mysql/addtime.html)         | 时间加法运算，在原始时间上添加指定的时间                     |
>   | [SUBTIME](http://c.biancheng.net/mysql/subtime.html)         | 时间减法运算，在原始时间上减去指定的时间                     |
>   | [DATEDIFF](http://c.biancheng.net/mysql/datediff.html)       | 获取两个日期之间间隔，返回参数 1 减去参数 2 的值             |
>   | [DATE_FORMAT](http://c.biancheng.net/mysql/date_format.html) | 格式化指定的日期，根据参数返回指定格式的值                   |
>   | [WEEKDAY](http://c.biancheng.net/mysql/weekday.html)         | 获取指定日期在一周内的对应的工作日索引                       |

### [流程控制函数](http://c.biancheng.net/mysql/function/#:~:text=%E6%95%B0%E6%8D%AE%E7%9A%84%E5%B9%B3%E5%9D%87%E5%80%BC-,MySQL%20%E6%B5%81%E7%A8%8B%E6%8E%A7%E5%88%B6%E5%87%BD%E6%95%B0,-%E5%87%BD%E6%95%B0%E5%90%8D%E7%A7%B0)

>   | 函数      | 作用                                                         | 备注                                                   |
>   | --------- | ------------------------------------------------------------ | ------------------------------------------------------ |
>   | IF        | 有三个参数,第一个参数为空/假，输出第三个参数；否则输出第二个参数 | /                                                      |
>   | IFNULL    | 有两个参数,第一个参数为空输出第二个参数,否则输出第一个       | 只能判断NULL或者非NULL不能判断真假值                   |
>   | CASE WHEN | 搜索语句                                                     | 流程控制运算符的作用是根据条件通过分支结构决定字段的值 |
>

#### IF

>   [MySQL](http://c.biancheng.net/mysql/) IF 语句允许您根据表达式的某个条件或值结果来执行一组 SQL 语句。
>
>   要在 MySQL 中形成一个表达式，可以结合文字，变量，运算符，甚至函数来组合。表达式可以返回 TRUE,FALSE 或 NULL，这三个值之一。
>
>   ###### 语法结构如下
>
>   ```sql
>   IF(expr,v1,v2)
>   ```
>
>   其中：表达式 expr 得到不同的结果，当 expr 为真是返回 v1 的值，否则返回 v2.
>
>   ![image-20230524001602834](./Mysql%20%E6%95%B0%E6%8D%AE%E5%BA%93.assets/image-20230524001602834.png)

#### IFNULL

>   IFNULL 函数是 MySQL 控制流函数之一，它接受两个参数，如果不是 NULL，则返回第一个参数。 否则，IFNULL 函数返回第二个参数。两个参数可以是文字值或表达式。
>
>   ###### 语法如下
>
>   ```sql
>   IFNULL(v1,v2);
>   ```
>
>   其中：如果 v1 不为 NULL，则 IFNULL 函数返回 v1; 否则返回 v2 的结果。
>
>   ![image-20230524001744340](./Mysql%20%E6%95%B0%E6%8D%AE%E5%BA%93.assets/image-20230524001744340.png)

#### CASE | WHEN

>   除了 [IF](http://c.biancheng.net/mysql/if.html) 函数，[MySQL](http://c.biancheng.net/mysql/) 还提供了一个替代的条件语句 CASE。 MySQL CASE 语句使代码更加可读和高效。
>
>   CASE 语句有两种形式：简单的和可搜索 CASE 语句。

##### 简单的 CASE 语句

>   简单的 CASE 语句就是指使用简单 CASE 语句来检查表达式的值与一组唯一值的匹配。
>
>   ###### 语法如下
>
>   ```sql
>   CASE  <表达式>
>      WHEN <值1> THEN <操作>
>      WHEN <值2> THEN <操作>
>      ...
>      ELSE <操作>
>   END CASE;
>   ```
>
>   其中：<表达式> 可以是任何有效的表达式。我们将 <表达式> 的值与每个 WHEN 子句中的值进行比较，例如 <值1>，<值2> 等。如果 <表达式> 和 <值n> 的值相等，则执行相应的 WHEN 分支中的命令 <操作>。如果 WHEN 子句中的 <值n> 没有与 <表达式> 的值匹配，则 ELSE 子句中的命令将被执行。ELSE 子句是可选的。 如果省略 ELSE 子句，并且找不到匹配项，MySQL 将引发错误。
>
>   ![image-20230524002124761](./Mysql%20%E6%95%B0%E6%8D%AE%E5%BA%93.assets/image-20230524002124761.png)
>
>   ##### 该示例涉及索引

##### 可搜索的 CASE 语句

>   简单 CASE 语句仅允许将表达式的值与一组不同的值进行匹配。 为了执行更复杂的匹配，如范围，则可以使用可搜索 CASE 语句。 可搜索 CASE 语句等同于 IF 语句，但是它的构造更加可读。
>
>   ###### 语法如下
>
>   ```sql
>   CASE
>       WHEN <条件1> THEN <命令>
>       WHEN <条件2> THEN <命令>
>       ...
>       ELSE commands
>   END CASE;
>   ```
>
>   MySQL 分别计算 WHEN 子句中的每个条件，直到找到一个值为 TRUE 的条件，然后执行 THEN 子句中的相应 <命令>。如果没有一个条件为 TRUE，则执行 ELSE 子句中的 <命令>。如果不指定 ELSE 子句，并且没有一个条件为 TRUE，MySQL 将发出错误消息。MySQL 不允许在 THEN 或 ELSE 子句中使用空的命令。 如果您不想处理 ELSE 子句中的逻辑，同时又要防止 MySQL 引发错误，则可以在 ELSE 子句中放置一个空的 BEGIN END 块。![image-20230524002200552](./Mysql%20%E6%95%B0%E6%8D%AE%E5%BA%93.assets/image-20230524002200552.png)
>
>   ##### 该示例涉及索引

# 运算符

>   ### MySQL 支持 4 种运算符，分别是：
>
>   ###### 算术运算符
>
>   执行算术运算，例如：加、减、乘、除等。
>
>   ###### 比较运算符
>
>   包括大于、小于、等于或不等于、等等。主要用于数值的比较、字符串的匹配等方面。
>
>   ###### 逻辑运算符
>
>   包括与、或、非和异或、等逻辑运算符。其返回值为布尔型，真值（1 或 true）和假值（0 或 false）。
>
>   ###### 位运算符
>
>   包括按位与、按位或、按位取反、按位异或、按位左移和按位右移等位运算符。位运算必须先将数据转换为补码，然后在根据数据的补码进行操作。运算完成后，将得到的值转换为原来的类型（十进制数），返回给用户。

## [算数运算符](http://c.biancheng.net/view/7189.html#:~:text=%E5%92%8C%E8%BF%90%E7%AE%97%E7%AC%A6-,MySQL%E7%AE%97%E6%9C%AF%E8%BF%90%E7%AE%97%E7%AC%A6,-%3C%20%E4%B8%8A%E4%B8%80%E8%8A%82)

| 运算符 | 作用               | 使用方法                           |
| ------ | ------------------ | ---------------------------------- |
| +      | 加法运算           | 用于获得一个或多个值的和           |
| -      | 减法运算           | 用于从一个值中减去另一个值         |
| *      | 乘法运算           | 使数字相乘，得到两个或多个值的乘积 |
| /，DIV | 除法运算，返回商   | 用一个值除以另一个值得到商         |
| %，MOD | 求余运算，返回余数 | 用一个值除以另一个值得到余数       |

## [比较运算符](http://c.biancheng.net/view/7191.html#:~:text=%E5%92%8C%E8%BF%90%E7%AE%97%E7%AC%A6-,MySQL%E6%AF%94%E8%BE%83%E8%BF%90%E7%AE%97%E7%AC%A6%E4%B8%80%E8%A7%88%E8%A1%A8%EF%BC%88%E5%B8%A6%E8%A7%A3%E6%9E%90%EF%BC%89,-%3C%20%E4%B8%8A%E4%B8%80%E8%8A%82)

|       运算符        |             名称             | 示例  |
| :-----------------: | :--------------------------: | :---: |
|          =          |             等于             | ID=5  |
|          >          |             大于             | ID>5  |
|          <          |             小于             | ID<5  |
|         >=          |           大于等于           | ID>=5 |
|         <=          |           小于等于           | ID<=5 |
|       !=或<>        |            不等于            | ID!=5 |
| IS NULL 或者 ISNULL |      判断一个值是否为空      |   /   |
|     IS NOT NULL     |     判断一个值是否不为空     |   /   |
|     BETWEEN AND     | 判断一个值是否落在两个值之间 |   /   |

## 逻辑运算符

| 运算符      | 作用     |
| ----------- | -------- |
| NOT 或者 !  | 逻辑非   |
| AND 或者 && | 逻辑与   |
| OR 和 \|\|  | 逻辑或   |
| XOR         | 逻辑异或 |

## [位运算符](http://c.biancheng.net/view/7195.html#:~:text=%E5%92%8C%E8%BF%90%E7%AE%97%E7%AC%A6-,MySQL%E4%BD%8D%E8%BF%90%E7%AE%97%E7%AC%A6,-%3C%20%E4%B8%8A%E4%B8%80%E8%8A%82)

| 运算符 | 说明   | 使用形式 | 举例                             |
| ------ | ------ | -------- | -------------------------------- |
| \|     | 位或   | a \| b   | 5 \| 8                           |
| &      | 位与   | a & b    | 5 & 8                            |
| ^      | 位异或 | a ^ b    | 5 ^ 8                            |
| ~      | 位取反 | ~a       | ~5                               |
| <<     | 位左移 | a << b   | 5 << 2，表示整数 5 按位左移 2 位 |
| >>     | 位右移 | a >> b   | 5 >> 2，表示整数 5 按位右移 2 位 |

## [运算符优先级](http://c.biancheng.net/view/7399.html#:~:text=%E5%92%8C%E8%BF%90%E7%AE%97%E7%AC%A6-,MySQL%E8%BF%90%E7%AE%97%E7%AC%A6%E7%9A%84%E4%BC%98%E5%85%88%E7%BA%A7,-%3C%20%E4%B8%8A%E4%B8%80%E8%8A%82)

| 优先级由低到高排列 | 运算符                                                       |
| ------------------ | ------------------------------------------------------------ |
| 1                  | !                                                            |
| 2                  | -(负号）、〜（位反转）                                       |
| 3                  | ^                                                            |
| 4                  | \*、/、%                                                      |
| 5                  | -(减号）、+                                                  |
| 6                  | <<、>>                                                       |
| 7                  | &                                                            |
| 8                  | \|                                                           |
| 9                  | =(比较运算）、<=>、>=、>、<=、<、<>、!=、 IS、LIKE、REGEXP、IN |
| 10                 | BETWEEN、CASE、WHEN、THEN、ELSE                              |
| 11                 | NOT                                                          |
| 12                 | &&、AND                                                      |
| 13                 | XOR                                                          |
| 14                 | II、OR                                                       |
| 15                 | =(赋值运算）、:=                                             |
