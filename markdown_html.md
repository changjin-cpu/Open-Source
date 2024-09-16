# Markdown与Html
## 介绍
Markdown 是一种轻量级标记语言，它允许人们使用易读易写的纯文本格式编写文档，然后转换成有效的 XHTML（或者 HTML）。Markdown 设计的初衷是为了让内容易于阅读和书写，它通过简单的文本格式来表示如标题、列表、链接、图片、代码块等复杂内容。Markdown 的语法简洁，易于学习，广泛应用于网络写作、文档编辑等领域。

HTML（HyperText Markup Language）是超文本标记语言，它是用于创建网页的标准标记语言。HTML 通过一系列的元素来定义网页的结构和内容，包括文本、图片、链接、表格等。HTML 文档由一系列的标签（tags）组成，这些标签告诉浏览器如何显示网页内容。
## 代码
```python
import re  
  
def markdown_to_html(text):  
    # 转换标题  
    text = re.sub(r'^# (.*?)$', r'<h1>\1</h1>', text, flags=re.MULTILINE)  
    text = re.sub(r'^## (.*?)$', r'<h2>\1</h2>', text, flags=re.MULTILINE)  
      
    # 转换加粗文本  
    text = re.sub(r'\*\*(.*?)\*\*', r'<strong>\1</strong>', text)  
      
    # 转换链接（简单示例，未处理完整 URL）  
    text = re.sub(r'\[(.*?)\]\((.*?)\)', r'<a href="\2">\1</a>', text)  
      
    # 转换段落（简单处理，仅作为示例）  
    text = re.sub(r'^(.+)$', r'<p>\1</p>', text, flags=re.MULTILINE)  
  
    return text  
  
# 示例 Markdown 文本  
markdown_text = """  
# 标题 1  
## 标题 2  
  
这是**加粗文本**。  
  
[这是一个链接](https://example.com)  
  
这是普通文本。  
"""  
  
# 转换并打印 HTML  
html_text = markdown_to_html(markdown_text)  
print(html_text)
```
