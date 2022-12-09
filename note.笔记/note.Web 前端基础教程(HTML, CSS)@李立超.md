---
title: note.Web 前端基础教程(HTML, CSS)@李立超
date: 28-11-2022
tags: category/computerScience/HTML, category/computerScience/CSS, category/computerScience/JavaScript
link: https://youtube.com/playlist?list=PLmOn9nNkQxJFs5KfK5ihVgb8nNccfkgxn
---


# Web 前端基础教程(HTML, CSS)

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

#### 2.1 css 注释 `/* */`

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

### 3 CSS 选择器 (Selectors)

#### 3.1 常用选择器 ( Simple Selectors)

##### 元素选择器 `p{}`

###### 作用
- 根据标签名来选中指定元素
###### 语法
- `标签名{}`
- 例: `p{} h1{} div{}`

##### ID 选择器 `#id{}`

###### 作用
- 根据元素的 id 属性选中一个元素

###### 语法
- `#id属性值{}`
- 注意: id 属性不可以命名两个元素, 因为 id 也在 JavaScript 里用, 如果有重复, 会有大隐患 . 

##### 类选择器 `.class{}`

	class 是一个标签属性, 它和 id 类似, 不同的是 class 可以重复使用, 可以通过 class 属性来为元素分组. 
	可以同时为一个元素, 制定多个 class. class名之间用空格隔开

###### 作用
- 根据元素的 class 属性选中一组元素

###### 语法
- `.class 属性值`

##### 通配选择器 `*{}`

###### 作用
- 选中页面中的所有元素

###### 语法
- `*{}`

```html
<!DOCTYPE html>

<html lang="en">

	<head>
	
		<meta charset="UTF-8">
		
		<meta http-equiv="X-UA-Compatible" content="IE=edge">
		
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		
		<title>Document</title>
	
	<style>
	
		/* 将所有段落设置为红色. */
		
		p{ color: red }
		
		h1{color: green}
		  
		/* 将一句话设置为橙色 */
	
		#orange{ color: orange }
	
		/* 将第三,第四句话设置为蓝色 */
	
	.blue{ color: blue }
	
	.abc{ font-size: 29px; }
	
	*{ 
	font-family: 
		'Gill Sans', 
		'Gill Sans MT', 
		Calibri, 
		'Trebuchet MS', 
		sans-serif;
		}
	
	</style>
	
</head>

<body>

	<h1 class="blue abc">我是标题</h1>
	
	<p>
	
	我是第一句话
	
	</p>
	
	<p id="orange">
	
	我是第二句话
	
	</p>
	
	<p class="blue">
	
	我是第三句话
	
	</p>
	
	<p class="blue">
	
	我是第四句话
	
	</p>

</body>

</html>
```


##### 交集选择器 `p.content{}`

###### 作用
- 选中同时复合多个条件的元素

###### 语法
- `选择器 1 选择器 2 选择器 n{}`

###### 注意
- 交集选择器中如果有元素选择器, 必须使用元素选择器开头. 


##### 并集选择器 ( 选择器分组) `p,div,.class,#id,h1.class,{}`

###### 作用
- 同时选择多个选择器对应的元素

###### 语法
- `选择器 1,选择器 2, 选择器 n{}`


```html
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta http-equiv="X-UA-Compatible" content="IE=edge">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Document</title>

<style>

/* 将 class 为 red 的元素设置为红色(字体) */

.red{

color: red;

}

/* 将 class 为 red 的 div 字体大小为 30px */

div.red{

font-size: 30px;

}

h1, span{

color: green

}

</style>

</head>

<body>

<div class="red">我是div</div>

<p class="red">我是 p 元素</p>

<div class="red2">我是div2</div>

<h1>标题</h1>

<span>哈哈</span>

</body>

</html>
```

##### 关系选择器

###### 网页之中不同元素之间的关系

- 父元素
	- 直接包含另一个元素的元素 .  
- 子元素
	- 直接被另一个元素包含的元素 . 
- 祖先元素
	- 直接或间接包含后代元素的元素 . 
	- 一个元素的父元素也是它的祖先元素 . 
- 后代元素
	- 直接或间接被祖先元素包含的元素叫后代元素 . 
	- 子元素也是后代元素 . 
- 兄弟元素
	- 拥有相同父元素的元素是兄弟元素

##### 子元素选择器

###### 作用
- 选中指定父元素的指定子元素

###### 语法
- `父元素 > 子元素`

##### 后代元素选择器

###### 作用
- 选中指定元素内的指定后代元素

###### 语法
- `祖先元素 后代元素`

##### 混合元素选择器

###### 作用
- 父子, 祖先后代混合选择

###### 语法
- `祖先元素 > 父元素 > 子元素`

##### 兄弟元素选择器

###### 作用
- 选择下一个兄弟
- 选择后面所有的兄弟

###### 语法
- `前一个 + 后一个`
- `第一个 ~ 后面所有`

### 3.2 属性选择器

- `[属性名]`
- 选择含有指定属性的元素

- `[属性名 = 属性值]`
- 选择含有指定属性与属性名的元素

- `[属性名^=属性值]`
- 选择属性值以指定值开头的元素

- `[属性名$=属性值]`
- 选择属性值以指定值结尾的元素

- `[属性名*=属性值]`
- 选择属性值含有指定值的元素

### 3.3 伪类选择器

#### 伪类

- 不存在的类, 特殊的类
- 用来描述一个元素的特殊状态
	- 比如: 第一个元素, 被点击的元素, 鼠标移入的元素

###### 特点

- 伪类一般情况下都是使用 `:` 开头


###### 语法

- `:first-child` 第一个子元素
- `:last-child` 最后一个子元素
- `nth-child(n)` 任意第 n 个子元素
	- 特殊值:
		- `n`;  第 n 个, n 的范围 0 ~ 正无穷
		- `2n` 或 `even`; 第偶数个, 2 * n
		- `2n+1`或 `odd`; 选中第奇数位的
- 以上这些伪类都是根据所有的子元素进行排序的 . 

	- `:first-of-type`
	- `:last-of-type`
	- `:nth-of-type`
-  这几个伪类和上述类似, 不过只在同类型元素中进行排序 . 

- `:not()` 否定伪类
	- 将符合条件的元素从选择器中去除

```html
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta http-equiv="X-UA-Compatible" content="IE=edge">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Document</title>

<style>

/* 将 ul 里的第一个 li 设置为红色 */

/* ul > li:first-of-type{

color: red

} */

  

ul > li:not(:nth-of-type(3)){

color: yellowgreen

}

</style>

</head>

<body>

<!-- ul>li 自动生成父子关系的标签 -->

<ul>

<li></li>

</ul>

  

<!-- ul+ul 自动生成兄弟关系的标签 -->

  

<ul></ul>

<ul></ul>

  

<!-- ul>li*5 自动生成无序列表包含五个元素 -->

  

<ul>

<span>我是一个 span</span>

<li>第零个</li>

<li>第一个</li>

<li>第二个</li>

<li>第三个</li>

<li>第四个</li>

<li>第五个</li>

</ul>

</body>

</html>
```


#### 其他伪类

```html
<!DOCTYPE html>

<html lang="en">

<head>

<meta charset="UTF-8">

<meta http-equiv="X-UA-Compatible" content="IE=edge">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Document</title>

<style>

/* :link 用来表示没访问过的链接(正常的链接) */

a:link{

color: red;

}

  

/*

:visited 用来表示访问过的链接

由于隐私的原因, :visited 这个伪类只能修改颜色, 除了特殊需要, 不建议更改.

*/

  

a:visited{

color: orange;

/* font-size: 50px; */

}

  

/* :hover 表示鼠标移入的状态. */

  

a:hover{

color: aqua;

font-size: 30px;

}

  

/* :active 表示鼠标点击的状态 */

  

a:active{

color: yellowgreen;

  

}

</style>

</head>

<body>

<!--

超链接的几种状态

1. 没有访问过的链接

2. 访问过的链接

  

访问过还是没访问过, 由用户的历史记录和 cookie 决定

-->

<a href="https://www.google123.com">访问过的连接</a>

<br><br>

<a href="https://www.google.com">没访问过的连接</a>

  

</body>

</html>
```


### 3.4 伪元素选择器

