---
tags:
  - JAVA/JAVA_WEB
  - 内容
日月: 2024-08-28
时分: 11:34
---
>[!info] 效果：
>
>未配置前：
>![[JAVA/JAVA Web/Tomcat/Files/30a4a66324af09f4f0be348a70cfb431.png]]
>配置后：
>![[JAVA/JAVA Web/Tomcat/Files/5c28ec90100a5e7387b85ae37a292dcf.png]]
### IDEA 中 Tomcat 日志显示乱码解决方法[^1]:
1. 双击Shift输入：`编辑自定义虚拟机选项/Edit custom vm options`![[JAVA/JAVA Web/Tomcat/Files/e1d553a0d56a32ed7594b9a11dc6cf69.png|400]]
2. 最后一行添加：`-Dfile.encoding=UTF-8`![[JAVA/JAVA Web/Tomcat/Files/c84d0e015d9805b08caf84bf3b9de0d0.png]]
3. 重启IDEA

[^1]: [idea启动tomcat控制台中文乱码的三种情况解决_java_脚本之家 (jb51.net)](https://www.jb51.net/program/2999982mw.htm)