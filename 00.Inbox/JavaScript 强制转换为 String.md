---
title: JavaScript 强制转换为 String
date: 28-12-2022
tags: 
aliases: 
---

# JavaScript 强制转换为 String

## 方式一:  

- 调用被转换数据类型的toString()方法.  
- 该方法不会影响到原变量, 它会将转换结果返回,  
- 但是注意, null 和 undefined 这两个值没有 toString() 方法,  
	- 如果调用,会报错.  

```js
var a = 123;  
console.log(typeof a);  
console.log(a);
```

- 调用 a 的 toString() 方法, 
- 或者说调用 xxx 的 yyy() 方法,就是 xxx.yyy(); 

```js
a.toString();
```

- 该方法不会改变原变量, 它会将结果返回

```js
console.log(typeof a);  
console.log(a);  
  
a = a.toString();  
console.log(typeof a);  
console.log(a);
```

#### 注意:
- Null 和 undefined 没有 toString() 方法

```js
//报错
a = null;  
a = a.toString(); 
console.log(typeof a);  
console.log(a);  

a = undefined;  
a = a.toString();  
console.log(typeof a);  
console.log(a);
```

## 方式二:  
- 调用 String()函数,并将转换的数据作为参数, 传递到函数  
	- 调用函数 : xxx();
	- 使用 String() 函数做强制类型转换时,  
	- 对于 Number 和 Boolean 实际上就是调用 toString() 方法  
		- 对于 null 和 undefined 就不会调用 toString() 方法  
		- 他会将 null 和 undefined 直接转换为 String "null" 和 "undefined"*

```js
a = 123;  
/* 调用String()函数, 来将 a 转换为字符串 */a = String(a);  
console.log(typeof a);  
console.log(a);  
  
console.log("*****************");  
a = null;  
a = String(a);  
console.log(typeof a);  
console.log(a);  
  
console.log("*****************");  
a = undefined;  
a = String(a);  
console.log(typeof a);  
console.log(a);
```