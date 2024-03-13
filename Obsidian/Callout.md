---
tags:
  - Obsidian/语法
时间: 2023-11-29
---
  >[!info] Obsidian 0.14.2 版本后增加了 Callout 功能，这个功能就是之前 Admonition (简称 ad 插件) 插件收编的，目前语法跟 Microsoft Docs 一致。之前用 ad 插件设置的提示框可以一键转换成最新的语法样式。
  
你可以参考英文原版，了解这个功能：[Use callouts](https://help.obsidian.md/How+to/Use+callouts)，也可以阅读下面的中文简要说明

在笔记中直接书写（无需代码块）如下内容：

```
> [!规定的标记]
```

这里规定的标记在对应的文章中查找，标记和样式是对应的。
如果可以输入标题，则这样：

```
> [!规定的标记] 标题内容
```

如果还可以输入内容：

```
> [!规定的标记] 标题内容
> 笔记内容，你会发现和 markdown 中的引用是相同的语法
>
> 比如分段也是这样空一行
```

---
### 目前支持的样式列表

左边为中文释义，右边为语法，每条当中效果一致，其他的单词就是别名：
- 笔记 (Note)，可以使用任意单词，最终渲染均为改样式
- 摘要，总结，TLDR (Abstract, Summary, TLDR)
- 提示，暗示，重要 (Tip, Hint, Important)
- 成功，检查，完成 (Success, Check, Done)
- 问题，帮助，常见问题 (Question, Help, FAQ)
- 警告，注意，提醒 (Warning, Caution, Attention)
- 失败，失败，缺失 (Failure, Fail, Missing)
- 危险，错误 (Danger, Error)
- 错误，漏洞 (Bug)
- 示例 (Example)
- 引用，引述 (Quote, Cite)

#### 官方示例
- 笔记 (Note)，可以使用任意单词，最终渲染均为改样式
> [!note] **Note**
> 
> Here’s a callout block.  
> It supports **markdown** and [wikilinks](https://pkmer.cn/Pkmer-Docsink).

- 摘要，总结，TLDR (Abstract, Summary, TLDR)
>[!abstract] 

- 信息，待办事项 (Info, Todo)
>[!todo] 

   >[!info] 

- 提示，暗示，重要 (Tip, Hint, Important)
>[!tip] 

- 成功，检查，完成 (Success, Check, Done)
>[!success] 

- 问题，帮助，常见问题 (Question, Help, FAQ)
>[!question] 

- 警告，注意，提醒 (Warning, Caution, Attention)
>[!warning]

- 失败，失败，缺失 (Failure, Fail, Missing)
>[!failure]

- 危险，错误 (Danger, Error)
>[!danger] 

- 错误，漏洞 (Bug)
>[!bug] 

- 示例 (Example)
>[!example] 

- 引用，引述 (Quote, Cite)
>[!quote] 

### 提示框的各种用法

- 可以没有内容直接显示标题
> [!tip] **Callouts can have custom titles** | callout可以有自定义标题
> Like this one. 像这个。

- 在 `[]` 后使用减号 `-` 创建可折叠提示框
> [!faq]- Are callouts foldable? 标注可以折叠吗?
> Yes! In a foldable callout, the contents are hidden when the callout is collapsed.
> 是的！在可折叠注解中，内容在折叠时处于隐藏状态。