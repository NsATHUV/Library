---
tags:
  - JAVA/内容
aliases: 
日月: 2024-04-16
时分: 08:33
---
JVM（Java虚拟机）、JRE（Java运行时环境）和JDK（Java开发工具包）是Java开发和运行环境中的三个重要组成部分，它们之间有一定的关系：

1. **JVM（ Java Virtual Machine，Java虚拟机 ）**：
   - JVM 是Java程序的核心，它是一个虚拟的计算机，可以执行Java字节码（即以 `.class` 文件形式存在的Java源代码编译后的中间码）。
   - JVM 负责将字节码转换为特定平台的本地机器码，并在特定平台上运行Java应用程序。
   - JVM 提供了内存管理、垃圾回收和安全等功能，以确保Java程序在不同的平台上具有一致的行为。

2. **JRE（ Java Runtime Environment， Java运行时环境）**：
   - JRE 包含了运行Java应用程序所需的一切：JVM、Java核心类库、运行时的配置文件等。
   - JRE 可以被视为运行Java程序所必需的最小环境，它不包含任何用于Java开发的工具（如编译器和调试器）。

3. **JDK（ Java Development Kit，Java开发工具包）**：
   - JDK 是Java开发人员使用的工具包，它包含了JRE以及许多用于开发Java应用程序的工具，如编译器（javac）、调试器（jdb）、JavaDoc生成器等。
   - JDK 提供了编译、调试、运行Java程序以及其他开发任务所需的一切。

关系：
- JDK 包含了 JRE，因此 JDK 中拥有所有 JRE 的功能，并且还包含了用于Java开发的工具。
- JRE 包含了 JVM，所以当你安装 JRE 时，你同时也安装了 JVM。
- JVM 是 JRE 的一部分，它是JRE中的核心组件，用于执行Java程序。

简而言之，JDK 包含了完整的Java开发和运行环境，JRE 是运行Java程序所需的最小环境，而JVM 则是Java程序运行的核心。