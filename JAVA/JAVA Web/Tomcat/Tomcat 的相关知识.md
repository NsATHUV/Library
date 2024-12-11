---
tags:
  - JAVA/JAVA_WEB/Tomcat
  - 内容
aliases: 
日月: 2024-11-19
时分: 19:14
---
### **Tomcat 的特点**

1. **轻量级**：相比于其他 Java EE 应用服务器（如 WildFly、WebLogic），Tomcat 更轻量，启动速度快，占用资源少。
2. **免费开源**：Tomcat 是开源软件，基于 Apache 许可证发布，无需付费即可使用。
3. **跨平台**：由于是用 Java 编写，Tomcat 可以运行在任何支持 Java 的操作系统上。
4. **扩展性强**：支持通过插件或自定义代码扩展功能，满足不同的应用场景。

---

### **Tomcat 的主要组件**

1. **Catalina**：核心 Servlet 容器，负责处理 HTTP 请求和响应。
2. **Coyote**：连接器组件，用于解析 HTTP 协议，将请求交给 Catalina 处理。
3. **Jasper**：JSP 引擎，负责将 JSP 文件编译为 Servlet。
4. **Cluster**：提供集群支持，适用于分布式部署。
5. **Manager 应用**：用于管理和监控 Tomcat 部署。

---

### **Tomcat 的常见用途**

1. **运行 Java Web 应用**：部署基于 Servlet 和 JSP 的应用。
2. **开发测试环境**：许多开发者将 Tomcat 用于本地开发和调试。
3. **小型生产环境**：适合轻量级应用，不需要完整的 Java EE 功能。

---

### **Tomcat 的版本**

Tomcat 根据支持的 Java 版本分为多个版本。
以下是各版本 **Tomcat** 对应的 **JDK** 支持情况的表格：

| **Tomcat 版本** | **支持的 JDK 版本**          | **支持的 Servlet 版本** | **支持的 JSP 版本** | **备注**                         |
|------------------|-----------------------------|--------------------------|---------------------|----------------------------------|
| **Tomcat 8.0**   | JDK 7 至 JDK 8              | Servlet 3.1             | JSP 2.3             | 已停止维护，不建议使用。         |
| **Tomcat 8.5**   | JDK 7 至 JDK 22（未来版本） | Servlet 3.1             | JSP 2.3             | 是 8.0 的延续版，长期支持版本。   |
| **Tomcat 9.0**   | JDK 8 至 JDK 22（未来版本） | Servlet 4.0             | JSP 2.3             | 增加 HTTP/2 支持。              |
| **Tomcat 10.0**  | JDK 8 至 JDK 22（未来版本） | Servlet 5.0             | JSP 3.0             | 迁移至 Jakarta EE 命名空间。     |
| **Tomcat 10.1**  | JDK 11 至 JDK 22（未来版本）| Servlet 6.0             | JSP 3.1             | 适配 Jakarta EE 10。             |
| **Tomcat 11.0**  | JDK 17 至 JDK 22（未来版本）| Servlet 7.0             | JSP 4.0             | 适配 Jakarta EE 11，开发中。     |

#### **说明**
1. **JDK 版本支持**：  
   - Tomcat 9 和 10 可以支持较新的 JDK 版本，例如 JDK 22。  
   - 新版 Tomcat 偏向支持 Jakarta EE 规范，而旧版支持传统 Java EE。  

2. **Servlet 与 JSP 版本**：  
   - 每个 Tomcat 版本均对应特定的 Servlet 和 JSP 规范版本。  
   - 其中，Tomcat 10 开始使用 **Jakarta EE**，需要注意迁移命名空间（如 `javax.*` 变为 `jakarta.*`）。

3. **未来兼容性**：  
   Tomcat 开发团队通常在发布新版本时尽量保证向前兼容，确保对新 JDK 的支持。

---

### **工作流程示意**

1. 浏览器发送 HTTP 请求。
2. Coyote 接收请求并解析。
3. Catalina 处理请求，根据映射调用相应的 Servlet。
4. 如果请求的是 JSP，Jasper 将 JSP 编译为 Servlet 并执行。
5. Catalina 将响应通过 Coyote 返回给客户端。

Tomcat 适合那些需要灵活性和轻量级解决方案的 Java Web 应用开发者。