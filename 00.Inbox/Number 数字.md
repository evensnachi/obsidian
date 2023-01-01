---
title: Number 数字
date: 27-12-2022
tags: 
aliases: Number, 数字
---

# Number 数字

- 在 js 中所有的数值都是 `Number` 类型.  
- 包括*整数*和*浮点数*.  

```js  
/* 数字 123 */
var a = 123;  
a = 456.789;  
/* 字符串 123*/
var b = "123";

console.log(a);  // 456.789
console.log(b);  // 123
```

- 可以使用 运算符typeof 来检查一个变量的类型  
	- 语法: `typeof 变量` 
- 检查字符串, 返回 `String`    
- 检查数值时, 返回 `Number`

```js
console.log(typeof a);  // Number
console.log(typeof b);  // String
```

- JS 中可以表示的最大的数字

```js
console.log(Number.MAX_VALUE);   // 1.7976931348623157e+308

```

- 如果使用 Number 表示的数字超过了最大值, 则会返回一个 `Infinity`.表示正无穷. 
- 使用 `typeof` 检查 `Infinity` 也会返回 `Number`
```js
a = Number.MAX_VALUE * Number.MAX_VALUE;  
console.log(a); // Infinity
    
a = Infinity;  
console.log(a); // Infinity
console.log(typeof a); //number
```

- `NaN` 是 `Number` 的数据类型, 意思是 Not a Number 

```js
a = "asd" * "gfds";  
console.log(a);  // NaN
console.log(typeof a); //number   
```

```js
a = Number.MIN_VALUE; //大于零的最小值  
console.log(a);    // 5e-324
```

- 在 JS 中整数的运算基本可以保证精确

```js
var c = 123 + 456;  
console.log(c);    // 579
```

- 使用 JS 进行浮点数运算, 可能得到一个不精确的结果.   
- 因为二进制不能精确表示 1/10
- 所以千万不要使用 JS 或者其它语言的浮点数进行金融等精确计算. 
  
```js
c = 0.1 + 0.2;  
console.log(c);  //0.30000000000000004
```
