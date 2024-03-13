---
tags:
  - C语言/内容
aliases:
  - dowhile
---
不像 **for** 和 **while** 循环，它们是在循环头部测试循环条件。在 C 语言中，**do...while** 循环是在循环的尾部检查它的条件。

 **do...while** 循环与 while 循环类似，但是 do...while 循环会确保至少执行一次循环。

 C 语言中 **do...while** 循环的语法：

 ```c
 do
 {
  statement(s);
 
 }while( condition );
 ```

 注意，条件表达式出现在循环的尾部，所以循环中的 statement(s) 会在条件被测试之前至少执行一次。

 如果条件为真，控制流会跳转回上面的 do，然后重新执行循环中的 statement(s)。这个过程会不断重复，直到给定条件变为假为止。

 流程图：

 ```mermaid
 graph TD
 A((开始))
 B[do代码块]
 C{条件}
 D((结束))
 A-->B
 B-->C
 C-->|如果条件为false|D
 C-->|如果条件为true|B
 ```
 