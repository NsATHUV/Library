---
tags:
  - JAVA/JAVA_WEB
  - 内容
日月: 2024-08-27
时分: 14:05
aliases:
---
# 什么是Tomcat

>[!info] 简介
>Apache Tomcat 是一个免费的开源软件，用于运行 Java Web 应用程序。它可以理解并处理 Java Servlet 和 JSP（JavaServer Pages），让你可以创建动态的网页和 Web 服务。
>## 主要特点：
>1. **运行 Java Web 应用**：Tomcat 能处理 Java 代码，用它来生成网页内容。
>2. **轻量级**：Tomcat 体积小，安装和配置都比较简单，适合开发和小型应用。
>3. **Web 服务器**：不仅能运行动态网页，还能作为一个普通的 Web 服务器来处理静态内容，如 HTML 和图片。
>4. **易于扩展**：你可以通过插件和配置来扩展 Tomcat 的功能。
>
>## 常见用途：
>- **开发和测试**：开发者用它来测试 Java Web 应用。
>- **中小型网站**：适合用在不需要复杂功能的小型网站上。
>
>总的来说，Tomcat 是一个简单易用的工具，帮助你运行 Java Web 应用程序。

---
# 配置 Tomcat

## 一、下载对应版本的 Tomcat

![[JAVA/JAVA Web/Tomcat/Tomcat 的相关知识#**Tomcat 的版本**|Tomcat 的相关知识]]

注意：每个 Tomcat 版本对 JDK 的支持可能会有所不同，尤其是在新的更新和发布后。建议在使用前查看 Tomcat 官方文档以获取最准确的信息。

## 二、配置环境变量

>[!success] ![[JAVA/JAVA Web/Tomcat/配置Tomcat环境变量|配置Tomcat环境变量]]

---
## 三（1）、使用新版 IDEA UI 的配置方法

### 1. 创建 Java Web 项目

1. 创建一个空的Java项目。
2. 按下 `F4` 或者右键项目根目录>选择“打开模块设置”![[JAVA/JAVA Web/Files/Pasted image 20240828111130.png|350]]
3. 跟着以下步骤完成操作：
	1. 点击“+”
	2. 选择Web
	3. 点击修正，创建工件
	4. 图示：![[JAVA/JAVA Web/Files/Pasted image 20240828111315.png|450]]

### 2. 配置 Tomcat 服务器

>[!info] **懒得打字了，图示教程。**

![[JAVA/JAVA Web/Tomcat/Files/Pasted image 20240828112643.png|800]]

![[JAVA/JAVA Web/Tomcat/Files/a5687bae7502e82554837b1d45901e6c.png]]
![[JAVA/JAVA Web/Tomcat/Files/Pasted image 20240828113035.png|800]]
![[JAVA/JAVA Web/Tomcat/Files/Pasted image 20240828113211.png]]
>[!warning] 刚配置完大概率乱码。[[JAVA/JAVA Web/Tomcat/Tomcat 乱码解决方法|Tomcat 乱码解决方法]]

---
## 三（2）、使用旧版IDEA UI 的配置方法

在 IntelliJ IDEA 中配置 Tomcat 服务器进行开发的步骤如下，以下将相关按钮和选项备注中文：

### 1. **添加 Tomcat 服务器**
- 打开 IntelliJ IDEA。
- 点击顶部菜单栏的 **File**（文件） > **Project Structure**（项目结构）。
- 在左侧导航栏中，选择 **Project**（项目）。
- 在 **SDKs**（SDKs）选项卡下，点击 **+** 号，选择 **Tomcat Server**（Tomcat 服务器）。
- 浏览到 Tomcat 安装目录，然后点击 **OK**（确定）。

### 2. **配置 Tomcat 服务器**
- 在 IDEA 窗口右上角，点击 **Add Configuration**（添加配置）。
- 点击左上角的 **+** 号，选择 **Tomcat Server**（Tomcat 服务器），然后选择 **Local**（本地）。
- 在 **Configuration**（配置）选项卡中：
  - **Name**（名称）: 设置你希望的服务器名称。
  - **Application server**（应用服务器）: 选择你之前添加的 Tomcat 服务器。
  - **JRE**: 选择你项目使用的 JDK 版本。

### 3. **设置部署工件**
- 在 **Deployment**（部署）选项卡中，点击 **+** 号，选择 **Artifact**（工件）。
- 选择你要部署的 Web 工件（如 `.war` 文件或 Exploded 形式的 Web 项目）。
- 确保勾选 **Build and Start**（构建并启动）。

### 4. **配置启动和停止命令**
- 在 **Server**（服务器）选项卡中，你可以选择 Tomcat 的启动和停止命令（通常默认设置已经足够）。
- 如果需要自定义 VM Options，可以点击 **Edit VM Options**（编辑 VM 选项）按钮进行编辑。

### 5. **配置服务器端口**
- 在 **Server**（服务器）选项卡下，你可以配置 Tomcat 的 HTTP 端口、JMX 端口等。默认情况下，HTTP 端口通常是 8080，可以根据需要修改。

### 6. **启动 Tomcat 服务器**
- 配置完成后，点击 **Apply**（应用）然后点击 **OK**（确定）。
- 在右上角的运行按钮旁边，选择你配置的 Tomcat 服务器，然后点击运行按钮来启动 Tomcat。

### 7. **调试和日志配置**
- IDEA 提供了强大的调试工具。可以直接在代码中设置断点，然后启动 Tomcat 服务器进入调试模式。
- 在运行 Tomcat 期间，IDEA 会显示 Tomcat 的日志输出，方便你查看和调试问题。

通过这些步骤，IntelliJ IDEA 中的 Tomcat 服务器就可以成功配置并且用于开发、测试和部署你的 Java Web 应用程序了。

[^1]: 撰写笔记时，使用的是JDK22，因此提供Tomcat11下载地址。[Apache Tomcat® - Apache Tomcat 11 Software 下载](https://tomcat.apache.org/download-11.cgi)