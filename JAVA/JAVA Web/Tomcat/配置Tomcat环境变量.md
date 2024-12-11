---
tags:
  - JAVA/JAVA_WEB
  - 内容
日月: 2024-11-18
时分: 15:44
aliases:
---
配置 Tomcat 环境变量是确保 Tomcat 能够在命令行中正确运行的关键步骤。以下是如何在 Windows 系统中配置 Tomcat 环境变量的详细步骤：

### 1. **下载并安装 Tomcat**
- 首先，你需要从 [Apache Tomcat 官方网站](https://tomcat.apache.org/) 下载适合你的版本。
- 解压下载的文件到你希望安装的位置，例如 `D:\Java_web\apache-tomcat-11.0.0-M24`。

### 2. **设置 `CATALINA_HOME` 环境变量**
`CATALINA_HOME` 是 Tomcat 的主要环境变量，指向 Tomcat 的安装目录。

#### 配置步骤：
1. **右键点击“此电脑”**，选择 **“属性”**。
2. 在弹出的窗口中，点击左侧的 **“高级系统设置”**。
3. 点击 **“环境变量”** 按钮。
4. 在 **“系统变量”** 部分，点击 **“新建”** 按钮。
   - **变量名**：`CATALINA_HOME`
   - **变量值**：Tomcat 的安装目录路径，例如 `D:\Java_web\apache-tomcat-11.0.0-M24`
5. 点击 **“确定”** 保存。

### 3. **配置 `JAVA_HOME` 环境变量**
`JAVA_HOME` 是 JDK 的主要环境变量，指向 JDK 的安装目录。

#### 配置步骤：
1. 在 **“环境变量”** 窗口中，找到 **“系统变量”** 部分，点击 **“新建”** 按钮。
   - **变量名**：`JAVA_HOME`
   - **变量值**：JDK 的安装目录路径，例如 `D:\APP\JDK`
2. 点击 **“确定”** 保存。

### 4. **配置 `PATH` 环境变量**
将 `CATALINA_HOME` 和 `JAVA_HOME` 添加到 `PATH` 环境变量中，方便在命令行直接调用 Tomcat 和 JDK 的命令。

#### 配置步骤：
1. 在 **“系统变量”** 部分，找到并选择 **`Path`** 变量，然后点击 **“编辑”** 按钮。
2. 在编辑窗口中，点击 **“新建”**，然后添加以下两项：
   - `%CATALINA_HOME%\bin`
   - `%JAVA_HOME%\bin`
3. 点击 **“确定”** 保存所有设置。

### 5. **验证配置是否成功**
1. 打开 **命令提示符** (cmd)。
2. 输入以下命令来验证 Tomcat 和 JDK 的环境变量是否配置正确：
   - `echo %CATALINA_HOME%`：显示的路径应为 Tomcat 的安装目录。
   - `echo %JAVA_HOME%`：显示的路径应为 JDK 的安装目录。
   - `java -version`：显示 JDK 的版本信息，确保正确配置。
   - `catalina.bat run`：启动 Tomcat 服务器，若成功启动则说明配置正确。

### 6. **常见问题解决**
- 如果 `java -version` 命令输出的版本不对，可能是 `Path` 环境变量中的顺序问题，确保 `JAVA_HOME\bin` 在 `Path` 变量中的优先级较高。
- 如果 `catalina.bat run` 命令提示找不到 Java 相关文件，检查 `JAVA_HOME` 和 `Path` 配置是否正确。

这样配置好 Tomcat 和 JDK 的环境变量后，你可以直接在命令行中启动 Tomcat，也可以在开发工具中方便地使用它们。