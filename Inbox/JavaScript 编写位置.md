---
title: JavaScript 编写位置
date: 27-12-2022
tags: 
aliases: 
---

# JavaScript 编写位置

## 三个位置  

### 标签内部属性

- 可以将 JS 代码编写到 `<button>` 按钮标签的 `onclick` 属性中, 点击的时候, JS 代码会执行. 

```html  
<button onclick="alert('执行 JS 代码');">
	执行 JS 代码
</button>  
```

- 可以将 JS 代码写在 `<a>` 超链接标签的 `href` 属性中, 这样当点击超链接时, 会执行 JS 代码.  

```html  
<a href="javascript: alert('执行 JS 代码');">
	执行 JS 代码
</a>  
```  

- **注意:** 虽然可以写到标签属性中, 但是他们属于结构与行为耦合, 不方便维护, 不推荐使用.  

### `<script>` 标签体中 

```html  
<script type="text/javascript">
	alert("script标签中的代码");
</script>  
```
### 外部 js 文件中

- 通过`<script>` 标签引入, 写到外部文件中, 可以在不同页面中同时引用, 也可以利用到浏览器的缓存机制, 推荐使用.  

```html   
<script src="script.js"> 
	alert("我是引入外部 js 文件的 script 标签") 
</script>  
```
- `<script>` 标签一旦用于引入外部文件, 就不能再编写代码,  即使编写了浏览器也会忽略.  
- 如果需要则可以再创建一个新的 `<script>` 标签用于编写内部代码