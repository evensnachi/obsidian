---
title: note.2022版JavaWeb教程@尚硅谷.封捷
date: 28-11-2022
tags: category/computerScience/javaWeb, type/note 
---

# 2022版JavaWeb教程

[VideoLink](https://youtube.com/playlist?list=PLmOn9nNkQxJGKsCUQt6CpDmE2SjBOyLkK)

## 01. JavaWeb 教程简介

## 02. HTML 介绍

![[Pasted image 20221128110857.png]]

## 03. HTML 中的基础标签

- html 页面由一对标签组成, `<html></html>`
	- `<html>` 称之为开始标签
		- `</html>` 称之为结束标签
- `html` 标签内部有两个子标签
	- `<head></head>`
		- `<title>` 表示页面标题
		- `<meta>` 标签中设置编码方式
- `<body></body>`
	- `<br/>` *break return* 换行标签是个单标签(自结束标签) : 开始标签和结束标签是同一个, 斜杠放在单词后面. 
	- `<p></p>` *paragraph* 标签是段落标签
	- `<image>` 标签是图片标签
		- `src=`*source* 是标签内属性: 需要在等号后面加引号写图片路径. 
		- `width=` 是标签内宽度属性
		- `height=`是高度属性
		- `alt=` *alternative* 是注释属性, 会让搜索引擎识别图片
	- `<h1></h1>` *header* 标题 从 1 到 6
- 列表标签 
	- `<ol></ol>` *order list* 有序列表
		- `li` *list item* 子标签, 列表元素

- 路径的问题
	- 相对路径: 相对与当前文件的其他资源的路径
		- 就是查询路径时是从本文件开始的
	- 绝对路径: 从根目录开始的, 文件的完整路径.
		- 就是查询路径时是从根目录开始的 
- HTML 是解释型语言, 不是编译型语言
	- JAVA 是编译型语言, 不可以有错误, 否则编译失败.
	- HTML 在无法解释代码的时候, 会跳过.  


```html
<html>
	<head>
		<title>网页的标题</title>
		<meta charset="UTF-8">
	</head>
	<body>
		Hello World ! <br/> 你好 HTML!
		<p> 这里是一个段落 </p>
		<p> 这里是第二个段落 </p>
		<img src="Unknow.jpg">
		
	</body>
</html>
```

