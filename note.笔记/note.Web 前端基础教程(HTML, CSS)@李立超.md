---
title: note.Web 前端基础教程(HTML, CSS)@李立超
date: 28-11-2022
tags: category/computerScience/HTML, category/computerScience/CSS, category/computerScience/JavaScript
---


# Web 前端基础教程(HTML, CSS)

[(Link)Web 前端基础教程(HTML, CSS)](https://youtube.com/playlist?list=PLmOn9nNkQxJFs5KfK5ihVgb8nNccfkgxn)



## HTML 


## CSS

### 1. css 简介

- 网页的三个部分
	- 结构 HTML
	- 表现 CSS
	- 行为 JS
- 所有外在显示的东西都属于表现, 用 CSS 控制
- CSS 层叠样式表
	- 分层的样式的列表
	- 网页时分层的, 因为我们看起来的网页是从上面向下看的. 
	- 通过 CSS 可以为网页的每一层分别设置样式.

#### 1.1 使用 CSS 修改元素的样式

##### 1.1.1 第一种方式 : 内联样式, 行内样式
- 在标签内部使用 style 属性来设置元素样式
	- 使用名值对, 名值之间用冒号连接
	- 每个样式都以分号结尾. 
- 在开发中不推荐使用
	- 内联样式只能对一个标签生效. 
	- 因为每个元素都需要单独设置, 非常麻烦, 并且如果元素太多, 基本无法手动完成. 
	- 而且迭代非常麻烦, 当样式发生变化时, 非常不方便. 
	- 最好是 HTML 和 CSS 越远越好


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

#####  1.1.2 第二种方式: 内部样式

- 将样式编写到 `<head>` 中的 `<style>` 标签里
- 在 head 中 写 css 样式, 要使用 css 选择器来选择元素, 并为其设置样式
	- 可以为多个标签设置样式
	- 并且修改时只修改一次, 即可全部应用
- 内部样式表更方便为样式重复使用
- 问题: 
	- 我们的内部样式表只能对一个网页起作用, 里面的样式不能跨页面使用. 

```html
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<title>Document</title>

<style>

p {

color :green;

font-size: 30px;

}

</style>

</head>

<body>

<p>

少小离家老大回, <br/>

乡音无改鬓毛衰,

</p>

  

</body>

</html>
```

##### 1.1.3 第三种方式: 外部样式表 ( 最佳实践)

- 可以将 css 样式编写到外部 css 样式文件里
	- 然后通过 `<link rel="stylesheet" href="./style.css">` 标签引入外部 css 文件
- 外部样式表需要通过 link 标签 进行引入, 意味着只要想使用这些样式的网页中都可以对其进行引用, 使样式可以在不同页面之间复用. 
- 将样式编写到外部的 CSS 文件中, 可以使用浏览器的缓存机制. 
	- 从而加快网页的加载速度, 提高用户体验. 
	- 多个网页文件, 同时引用一个 css 文件, 那么浏览器只需要加载一次, 提高渲染速度. 

```html
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta http-equiv="X-UA-Compatible" content="IE=edge">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Document</title>

<link rel="stylesheet" href="./style.css">

</head>

<body>

<p>

少小离家老大回,

乡音无改鬓毛衰,

</p>

</body>

</html>
```

```css
p{

color: tomato;

font-size: 100px;

}
```


### 2. CSS 语法

#### 2.1 css 注释

- 在`<head>` 里的`<style>` 标签内部, 属于 CSS 的语法部分. 
	- 所以 HTML 就不能用了. 
	- CSS 的注释, 应当为 `/* */`
	- 会自动被浏览器忽略. 

#### 2.2 css 基本语法

##### 2.2.1 css 选择器

- 通过选择器, 可以选中页面中的指定元素. 
	- `p` 就是选中页面中的 p 元素

```html
<!DOCTYPE html>
<html lang="en">
<head>
	<meta charset="UTF-8">
	<meta http-equiv="X-UA-Compatible" content="IE=edge">
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>Document</title>
	<style>
		p{
		
		}
	</style>
</head>

<body>
	<p>少小离家老大回,乡音无改鬓毛衰, </p>
</body>

</html>
```

##### 2.2.2.2 css 声明块

- 通过声明块来**制定**要为元素设置的样式. 
	- **声明块**由一个一个的*声明*组成. 
	- **声明**是一个*名值对结构*, 一个样式名对应一个样式值. 
		- 名和值之间以*冒号连接*. 
		- 以*分号结尾* . 

### 3 CSS 选择器

#### 3.1 常用选择器

