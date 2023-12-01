---
tags:
  - C语言/内容
---
一个 **switch** 语句允许测试一个变量等于多个值时的情况。每个值称为一个 case，且被测试的变量会对每个 **switch case** 进行检查。

- switch 语句也属于多分支结构。

 ```c
 switch(expression){
   case constant-expression  :
      statement(s);
      break; /* 可选的 */
   case constant-expression  :
      statement(s);
      break; /* 可选的 */
 
   /* 您可以有任意数量的 case 语句 */
   default : /* 可选的 */
      statement(s);
 }
 ```

 **switch** 语句必须遵循下面的规则：

 -   **switch** 语句中的 **expression** 是一个常量表达式，必须是一个整型或枚举类型。
 -   在一个 switch 中可以有任意数量的 case 语句。每个 case 后跟一个要比较的值和一个冒号。
 -   case 的 **constant-expression** 必须与 switch 中的变量具有相同的数据类型，且必须是一个常量或字面量。
 -   当被测试的变量等于 case 中的常量时，case 后跟的语句将被执行，直到遇到 **[[break 和 continue#break|break]]** 语句为止。
 -   当遇到 **break** 语句时，switch 终止，控制流将跳转到 switch 语句后的下一行。
 -   不是每一个 case 都需要包含 **break**。如果 case 语句不包含 **break**，控制流将会 *继续* 后续的 case，直到遇到 break 为止。
 -   一个 **switch** 语句可以有一个可选的 **default** case，出现在 switch 的结尾。default case 可用于在上面所有 case 都不为真时执行一个任务。default case 中的 **break** 语句不是必需的。

 ```mermaid
 graph TB
 A((开始))
 A-->B{常量表达式}
 B-->|case 1|C(符合并开始执行代码块1)
 C-->|case 2|D(符合并开始执行代码块2)
 D-->|case 3|E(符合并开始执行代码块3)
 E-->|都不符合时执行default|F(代码块default)
 C-->|遇到break语句|G((结束))
 D-->|遇到break语句|G
 E-->|遇到break语句|G
 F-->|遇到break语句|G
 ```
