---
tags:
  - 内容
aliases:
  - mime
---
MIME（Multipurpose Internet Mail Extensions）是一种标准，用于描述在互联网上传输的数据的性质和格式。MIME类型或MIME媒体类型是一种标识数据类型的字符串，它通常由两部分组成：主要类型和子类型，它们之间由斜杠分隔。MIME类型的目的是确保计算机能够正确地识别和处理不同类型的数据，如文本、图像、音频、视频和其他多媒体内容。

以下是MIME类型的一些常见示例：

- `text/plain`：纯文本文件。
- `text/html`：HTML文档。
- `image/jpeg`：JPEG图像。
- `audio/mpeg`：MPEG音频文件。
- `video/mp4`：MP4视频文件。
- `application/pdf`：PDF文档。
- `application/json`：JSON数据。
- `application/xml`：XML数据。

MIME类型在互联网通信中扮演着关键的角色，特别是在HTTP协议中，它用于确定服务器发送的数据类型以及浏览器如何正确地处理这些数据。当你在Web浏览器中请求一个网页时，服务器通常会使用`Content-Type`标头来指定响应的MIME类型，从而告诉浏览器如何解释和呈现该页面的内容。

MIME类型还在电子邮件系统中广泛使用，用于标识电子邮件中的附件类型，确保邮件客户端能够正确地打开和显示附件。

总之，MIME是一种用于描述数据类型和格式的标准，它在互联网通信、电子邮件和多媒体内容传输中发挥着关键作用，确保不同系统能够正确地处理和呈现各种数据类型。