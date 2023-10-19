---
tags:
  - 案例
---
#HTML案例

```HTML
<!DOCTYPE html>
<html>
<head>
  <title>多类型输入字段示例</title>
</head>
<body>
  <h2>多类型输入字段示例</h2>
  <form action="process.php" method="post">
    <label for="text-input">文本输入：</label>
    <input type="text" id="text-input" name="text-input" />

    <br>

    <label for="password-input">密码输入：</label>
    <input type="password" id="password-input" name="password-input" />

    <br>

    <label for="number-input">数字输入（10 到 50）：</label>
    <input type="number" id="number-input" name="number-input" min="10" max="50" />

    <br>

    <label>单选按钮：</label>
    <input type="radio" id="radio1" name="gender" value="male">
    <label for="radio1">男性</label>
    <input type="radio" id="radio2" name="gender" value="female">
    <label for="radio2">女性</label>

    <br>

    <label>复选框：</label>
    <input type="checkbox" id="checkbox1" name="fruits[]" value="apple">
    <label for="checkbox1">苹果</label>
    <input type="checkbox" id="checkbox2" name="fruits[]" value="banana">
    <label for="checkbox2">香蕉</label>
    <input type="checkbox" id="checkbox3" name="fruits[]" value="cherry">
    <label for="checkbox3">樱桃</label>

    <br>

    <label for="email-input">电子邮件输入：</label>
    <input type="email" id="email-input" name="email-input" />

    <br>

    <label for="url-input">URL 输入：</label>
    <input type="url" id="url-input" name="url-input" />

    <br>

    <label for="date-input">日期输入：</label>
    <input type="date" id="date-input" name="date-input" />

    <br>

    <label for="file-input">文件上传：</label>
    <input type="file" id="file-input" name="file-input" />

    <br>

    <input type="submit" value="提交">
  </form>
</body>
</html>
```