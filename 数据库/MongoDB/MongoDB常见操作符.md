---
tags:
  - MongoDB/内容
aliases: 
日月: 2024-03-14
时分: 19:36
---
### 比较操作符

| 操作符     | 描述       | 例子                                      |
| ------- | -------- | --------------------------------------- |
| `$eq`   | 等于       | `{ field: { $eq: value } }`             |
| `$ne`   | 不等于      | `{ field: { $ne: value } }`             |
| `$gt`   | 大于       | `{ field: { $gt: value } }`             |
| `$gte`  | 大于等于     | `{ field: { $gte: value } }`            |
| `$lt`   | 小于       | `{ field: { $lt: value } }`             |
| `$lte`  | 小于等于     | `{ field: { $lte: value } }`            |
| `$in`   | 在指定的数组中  | `{ field: { $in: [value1, value2] } }`  |
| `$nin`  | 不在指定的数组中 | `{ field: { $nin: [value1, value2] } }` |
| `$size` | 匹配数组长度   | `{ field: { $size: value } }`           |

---
### 逻辑操作符

| 操作符       | 描述                 | 例子                                                    |
|--------------|----------------------|---------------------------------------------------------|
| `$and`       | 逻辑与               | `{ $and: [ { condition1 }, { condition2 } ] }`          |
| `$or`        | 逻辑或               | `{ $or: [ { condition1 }, { condition2 } ] }`           |
| `$not`       | 逻辑非               | `{ field: { $not: { condition } } }`                    |
| `$nor`       | 逻辑或非             | `{ $nor: [ { condition1 }, { condition2 } ] }`          |

---
### 元素操作符

| 操作符       | 描述                 | 例子                                                    |
|--------------|----------------------|---------------------------------------------------------|
| `$exists`    | 判断字段是否存在     | `{ field: { $exists: true } }`                          |
| `$type`      | 判断字段的类型       | `{ field: { $type: "string" } }`                        |

---
### 数组操作符

| 操作符       | 描述                     | 例子                                                    |
|--------------|--------------------------|---------------------------------------------------------|
| `$all`       | 匹配包含指定元素的数组   | `{ field: { $all: [value1, value2] } }`                 |
| `$elemMatch` | 匹配数组中满足指定条件的元素 | `{ field: { $elemMatch: { condition } } }`          |

---
### 文本搜索操作符

|操作符|描述|例子|
|---|---|---|
|`$text`|执行全文本搜索|`{ $text: { $search: "searchString" } }`|
|`$regex`|使用正则表达式匹配字符|`{ field: { $regex: /pattern/, $options: 'i' } }`|
|`$option`|正则表达式匹配选项|`{ field: { $regex: /pattern/, $options: 'i' } }`|
- `$option`是一个占位符，用于表示正则表达式中可以使用的匹配选项。例如，如果你想要使用不区分大小写的匹配，你可以将`$option`替换为`'i'`。完整的例子就是上面给出的`$regex`操作符的例子。请注意，`$option`不是一个单独的操作符，而是与`$regex`一起使用的参数。

---
### 地理空间操作符

| 操作符              | 描述      | 例子                                                                                                                         |
| ---------------- | ------- | -------------------------------------------------------------------------------------------------------------------------- |
| `$geoWithin`     | 在指定区域内  | `{ field: { $geoWithin: { $geometry: { type: "Polygon", coordinates: [ [ [0, 0], [3, 6], [6, 1], [0, 0] ] ] } } } }`       |
| `$geoIntersects` | 与指定区域相交 | `{ field: { $geoIntersects: { $geometry: { type: "Polygon", coordinates: [ [ [0, 0], [3, 6], [6, 1], [0, 0] ] ] } } } }`   |
| `$near`          | 附近      | `{ field: { $near: { $geometry: { type: "Point", coordinates: [longitude, latitude] }, $maxDistance: distance } } }`       |
| `$nearSphere`    | 在球形区域附近 | `{ field: { $nearSphere: { $geometry: { type: "Point", coordinates: [longitude, latitude] }, $maxDistance: distance } } }` |

---
### 位操作符

| 操作符       | 描述                 | 例子                                                    |
|--------------|----------------------|---------------------------------------------------------|
| `$bit`       | 位操作符             | `{ field: { $bit: { and: 5 } } }`                       |

---
### 更新操作符

| 操作符            | 描述                     | 例子                                                   |
| -------------- | ---------------------- | ---------------------------------------------------- |
| `$set`         | 设置字段的值                 | `{ $set: { field: value } }`                         |
| `$unset`       | 删除字段                   | `{ $unset: { field: "" } }`                          |
| `$inc`         | 增加字段的值                 | `{ $inc: { field: value } }`                         |
| `$mul`         | 乘以字段的值                 | `{ $mul: { field: value } }`                         |
| `$push`        | 向数组添加元素                | `{ $push: { field: value } }`                        |
| `$addToSet`    | 向数组添加元素，但不会重复          | `{ $addToSet: { field: value } }`                    |
| `$pull`        | 从数组中删除元素               | `{ $pull: { field: value } }`                        |
| `$pullAll`     | 从数组中删除指定值              | `{ $pullAll: { field: [value1, value2] } }`          |
| `$pop`         | 从数组中删除第一个或最后一个元素       | `{ $pop: { field: 1 } }` 或 `{ $pop: { field: -1 } }` |
| `$rename`      | 重命名字段                  | `{ $rename: { old_field: new_field } }`              |
| `$currentDate` | 设置字段为当前日期              | `{ $currentDate: { field: true } }`                  |
#### 加减乘除
在 MongoDB 更新操作中，通常没有直接提供除法运算的操作符。但是，你可以通过使用 `$mul` 操作符和逆操作来实现除法运算。例如，如果你想将字段的值除以某个数，你可以乘以该数的倒数。

以下是常见的加减乘除操作的示例：

- **加法示例：**

```json
{ $inc: { field: value } }
```

- **减法示例：**

```json
{ $inc: { field: -value } }
```

- **乘法示例：**

```json
{ $mul: { field: value } }
```

- **除法示例：**

```json
{ $mul: { field: 1/value } }
```

请注意，这里的 `field` 是要进行操作的字段，`value` 是要进行加减乘除的数值。

---
### 聚合操作符

| 操作符         | 作用               | 示例                                                                                                     |
| ----------- | ---------------- | ------------------------------------------------------------------------------------------------------ |
| `$sum`      | 对指定字段的值求和        | `{ $group: { _id: "$category", totalQuantity: { $sum: "$quantity" } } }`                               |
| `$avg`      | 对指定字段的值求平均值      | `{ $group: { _id: "$category", avgPrice: { $avg: "$price" } } }`                                       |
| `$max`      | 获取指定字段的最大值       | `{ $group: { _id: "$category", maxPrice: { $max: "$price" } } }`                                       |
| `$min`      | 获取指定字段的最小值       | `{ $group: { _id: "$category", minPrice: { $min: "$price" } } }`                                       |
| `$first`    | 获取每个组中指定字段的第一个值  | `{ $group: { _id: "$category", firstItem: { $first: "$name" } } }`                                     |
| `$last`     | 获取每个组中指定字段的最后一个值 | `{ $group: { _id: "$category", lastItem: { $last: "$name" } } }`                                       |
| `$addToSet` | 将值添加到一个集合中，去除重复值 | `{ $group: { _id: "$category", uniqueItems: { $addToSet: "$name" } } }`                                |
| `$push`     | 将值添加到一个数组中       | `{ $group: { _id: "$category", items: { $push: "$name" } } }`                                          |
| `$project`  | 对文档进行投影操作        | `{ $project: { name: 1, age: 1 } }`                                                                    |
| `$match`    | 对文档进行筛选操作        | `{ $match: { status: "A" } }`                                                                          |
| `$sort`     | 对文档进行排序操作        | `{ $sort: { age: -1 } }`                                                                               |
| `$limit`    | 限制聚合返回的文档数量      | `{ $limit: 5 }`                                                                                        |
| `$unwind`   | 展开数组类型的字段        | `{ $unwind: "$tags" }`                                                                                 |
| `$lookup`   | 在多个集合之间进行关联查询    | `{ $lookup: { from: "anotherCollection", localField: "field", foreignField: "field", as: "output" } }` |
#### `$category`

`$category`的含义是在MongoDB的聚合操作中==引用字段名为`category`的意思==。实际使用时，它代表了要在聚合操作中处理的文档的某个字段，您可以根据自己的需求将其替换为实际存在的字段名。

在聚合操作中，您可以使用`$category`来按照文档的`category`字段进行分组、筛选、计算总和等操作，例如：

- `{ $group: { _id: "$category", totalQuantity: { $sum: "$quantity" } } }`：按照`category`字段的值进行分组，并计算每个组内`quantity`字段值的总和。
- `{ $match: { category: "electronics" } }`：筛选出`category`字段值为“electronics”的文档。
- `{ $project: { categoryName: "$category" } }`：将`category`字段重命名为`categoryName`。
- `{ $sort: { categoryName: 1 } }`：按照`category`字段的值进行升序排序。

总之，`$category`在聚合操作中用于引用文档的某个字段，您可以根据需要将其替换为实际的字段名来执行聚合操作。

---
### 投影操作符

| 操作符       | 描述                 | 例子                                                    |
|--------------|----------------------|---------------------------------------------------------|
| `$`          | 投影操作符           | `{ field: 1, _id: 0 }`                                  |
投影操作符在 MongoDB 中用于控制返回文档中包含的字段。通过投影操作符，您可以指定只返回文档中特定字段，或排除某些字段，以满足查询需求，减少网络传输和数据处理的开销。

投影操作符的主要作用有两个方面：

1. **指定返回的字段**：您可以使用投影操作符 `$` 来指定要返回的字段，将其设置为 `1` 表示包含，`0` 表示排除。默认情况下，文档中的所有字段都会被返回，但通过投影操作符可以选择性地返回字段，减少返回文档的数据量。

2. **排除特定字段**：除了指定要返回的字段外，您还可以使用投影操作符将特定字段排除在返回结果之外。将字段设置为 `0` 表示排除该字段，其他字段会被返回。

下面是一个具体的例子来说明投影操作符的用法：

假设有一个名为 `users` 的集合，包含以下文档：

```json
{ "_id": 1, "name": "Alice", "age": 30, "email": "alice@example.com" }
{ "_id": 2, "name": "Bob", "age": 25, "email": "bob@example.com" }
{ "_id": 3, "name": "Charlie", "age": 35, "email": "charlie@example.com" }
```

如果您只想返回用户的名称和年龄，可以使用投影操作符将 `name` 和 `age` 字段设置为 `1`，而其他字段设置为 `0`（不返回）：

```javascript
db.users.find({}, { _id: 0, name: 1, age: 1 })
```

这将返回：

```json
{ "name": "Alice", "age": 30 }
{ "name": "Bob", "age": 25 }
{ "name": "Charlie", "age": 35 }
```

如此一来，您可以灵活地控制返回结果中包含的字段，以满足具体的查询需求，同时避免传输和处理不必要的数据。

---
