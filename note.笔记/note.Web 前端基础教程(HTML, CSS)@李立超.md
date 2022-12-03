---
title: note.Web 前端基础教程(HTML, CSS)@李立超
date: 28-11-2022
tags: category/computerScience/HTML, category/computerScience/CSS, category/computerScience/JavaScript
---


# Web 前端基础教程(HTML, CSS)

[(Link)Web 前端基础教程(HTML, CSS)](https://youtube.com/playlist?list=PLmOn9nNkQxJFs5KfK5ihVgb8nNccfkgxn)



## HTML 


## CSS

### 01 css 简介

- 网页的三个部分
	- 结构 HTML
	- 表现 CSS
	- 行为 JS
- 所有外在显示的东西都属于表现, 用 CSS 控制
- CSS 层叠样式表
	- 分层的样式的列表
	- 网页时分层的, 因为我们看起来的网页是从上面向下看的. 
	- 通过 CSS 可以为网页的每一层分别设置样式.

#### 使用 CSS 修改元素的样式
##### 第一种方式 : 内联样式, 行内样式
- 在标签内部使用 style 属性来设置元素样式
	- 使用名值对, 名值之间用冒号连接
	- 每个样式都以分号结尾. 
- 在开发中不推荐使用
	- 内联样式只能对一个标签生效. 
	- 因为每个元素都需要单独设置, 非常麻烦, 并且如果元素太多, 基本无法手动完成. 

```html
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<title>Document</title>

</head>

<body>

<p style="color :red; font-size: 30px;">少小离家老大回,乡音无改鬓毛衰,</p>

</body>

</html>
```
