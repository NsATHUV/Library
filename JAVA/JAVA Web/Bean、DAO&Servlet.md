---
tags:
  - JAVA/JAVA_WEB
  - 内容
aliases: 
日月: 2024-08-30
时分: 10:58
---
在Java Web开发中，**Bean**、**DAO**、和**Servlet**是常用的概念，它们各自承担不同的职责，在[[JAVA/JAVA Web/MVC架构|MVC]]（Model-View-Controller）架构中发挥着重要作用。以下是对这些概念的详细解释：

### 1. **Bean**
   - **Bean** 是一个用于封装数据的Java对象，通常遵循JavaBean规范。一个典型的Bean类包括以下几个特征：
     - **私有属性**：Bean中的数据通常通过私有属性来存储。
     - **公共getter和setter方法**：提供`get`和`set`方法来访问和修改这些属性。
     - **无参数构造方法**：Bean类通常需要一个无参数的构造方法，以便在Java EE框架中可以方便地实例化它。

   **示例：**
   ```java
   public class UserBean {
       private String username;
       private String password;

       public UserBean() {
           // 无参构造函数
       }

       public String getUsername() {
           return username;
       }

       public void setUsername(String username) {
           this.username = username;
       }

       public String getPassword() {
           return password;
       }

       public void setPassword(String password) {
           this.password = password;
       }
   }
   ```

   - **用法**：Bean通常用来传递数据，例如表单数据，或从数据库查询的结果，可以在Servlet或JSP页面中使用。

### 2. **DAO (Data Access Object)**
   - **DAO** 模式是用于将数据访问逻辑与业务逻辑分离的一种设计模式。DAO类负责与数据库进行交互，执行增、删、改、查（CRUD）操作。
   - **职责**：
     - **连接数据库**：DAO类通常负责管理与数据库的连接。
     - **执行SQL查询**：DAO类包含方法，用于执行针对数据库的SQL查询。
     - **返回数据对象**：DAO类将查询结果封装在Bean对象中，并返回给业务层或其他使用者。

   **示例：**
   ```java
   import java.sql.*;

   public class UserDAO {
       public UserBean getUser(String username) {
           UserBean user = null;
           try {
               // 假设数据库连接已建立
               Connection con = DriverManager.getConnection("jdbc:mysql://localhost:3306/testdb", "user", "password");
               String query = "SELECT * FROM users WHERE username = ?";
               PreparedStatement ps = con.prepareStatement(query);
               ps.setString(1, username);
               ResultSet rs = ps.executeQuery();

               if (rs.next()) {
                   user = new UserBean();
                   user.setUsername(rs.getString("username"));
                   user.setPassword(rs.getString("password"));
               }

               rs.close();
               ps.close();
               con.close();
           } catch (SQLException e) {
               e.printStackTrace();
           }
           return user;
       }
   }
   ```

   - **用法**：DAO类通常在Servlet中调用，用于从数据库获取数据或将数据保存到数据库中。

### 3. **Servlet**
   - **Servlet** 是Java Web应用程序中的一种服务器端组件，用于处理HTTP请求和响应。Servlet作为控制层，通常接收客户端的请求，调用相应的业务逻辑（如通过DAO访问数据库），并将结果返回给客户端（通常通过JSP呈现）。
   - **职责**：
     - **处理请求**：Servlet接收来自客户端的请求，并根据请求的类型（GET、POST等）调用不同的方法（如`doGet()`、`doPost()`）。
     - **调用业务逻辑**：Servlet通常会调用业务逻辑层或DAO类来处理请求中的数据。
     - **响应客户端**：Servlet将处理结果返回给客户端，通常会将结果转发到一个JSP页面进行显示。

   **示例：**
   ```java
   import java.io.IOException;
   import javax.servlet.*;
   import javax.servlet.http.*;

   public class LoginServlet extends HttpServlet {
       protected void doPost(HttpServletRequest request, HttpServletResponse response)
               throws ServletException, IOException {
           String username = request.getParameter("uname");
           String password = request.getParameter("pwd");

           UserDAO userDao = new UserDAO();
           UserBean user = userDao.getUser(username);

           if (user != null && user.getPassword().equals(password)) {
               // 登录成功，跳转到成功页面
               response.sendRedirect("success.jsp");
           } else {
               // 登录失败，跳转回登录页面
               response.sendRedirect("login.jsp");
           }
       }
   }
   ```

   - **用法**：Servlet负责处理客户端的请求，比如用户登录、表单提交等，然后根据请求调用相应的业务逻辑并返回结果。

### 总结：
- **Bean**：用于封装数据，通常代表一个实体或表单数据。
- **DAO**：数据访问对象，封装了与数据库交互的逻辑。
- **Servlet**：控制层组件，负责处理客户端请求并协调其他组件（如Bean和DAO）完成业务逻辑。