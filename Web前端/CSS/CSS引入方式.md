---
tags:
  - 内容
  - CSS/基础
aliases:
  - .css
日月: 2024-11-24
时分: 19:35
---
CSS可以通过三种不同的引入方式来应用到HTML文档中，分别是行内样式、内部样式表和外部样式表。以下是对这三种引入方式的介绍：

# 行内样式（Inline Styles）：
   - **描述**：行内样式是直接应用于HTML元素的样式，通过在HTML标签内的`style`属性中指定样式规则。
   - **示例**：
     ```html
     <p style="color: blue; font-size: 16px;">这是一段蓝色文本。</p>
     <div style="background-color: #FFA500; padding: 10px;">这是一个橙色背景的区块。</div>
     ```
   - **特点**：
     - 样式规则与特定元素紧密绑定。
     - 适用于个别元素的样式修改。
     - 可以在HTML文档中多次使用。

# 内部样式表（Internal Stylesheet）：
   - **描述**：内部样式表是在HTML文档的`<head>`部分使用`<style>`标签定义的样式表，通过在`<style>`标签内编写CSS规则来指定样式。
   - **示例**：
     ```html
     <head>
       <style>
         p {
           color: red;
           font-size: 18px;
         }
         .highlight {
           background-color: yellow;
         }
       </style>
     </head>
     <body>
       <p>这是一段红色文本。</p>
       <p class="highlight">这是一个带黄色背景的区块。</p>
     </body>
     ```
   - **特点**：
     - 样式规则定义在HTML文档内部，但可以应用到多个元素。
     - 适用于单个HTML文档的样式定义。

# 外部样式表（External Stylesheet）：
   - **描述**：外部样式表是一个独立的.css文件，其中包含了网站中的所有样式规则。这些样式规则可以通过HTML文档的[[Web前端/CSS/Link标签|链接标签]]（`<link>`）引入。
   - **示例**：
     创建一个名为`styles.css`的外部样式表文件，然后在HTML文档中引入：
     ```html
     <head>
       <link rel="stylesheet" type="text/css" href="styles.css">
     </head>
     <body>
       <p>这是一段应用外部样式表的文本。</p>
       <div class="custom-box">这是一个自定义样式的区块。</div>
     </body>
     ```
   - **特点**：
     - 样式规则存储在独立的.css文件中，可以在多个HTML文档中共享。
     - 适用于整个网站的一致性样式。
     - 更易于维护和更新。

总的来说，行内样式适合用于少量元素的快速样式修改，内部样式表适合单个HTML文档的样式定义，而外部样式表适合在整个网站中维护一致的样式。选择适当的样式引入方式取决于你的项目需求和组织结构。
