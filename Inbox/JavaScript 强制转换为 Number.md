---
title: JavaScript 强制转换为 Number
date: 28-12-2022
tags: 
aliases: 
---

# JavaScript 强制转换为 Number

```js
let a;  
a = "123";  
console.log(typeof a);  // String
console.log(a); // 123
```

## 方法一: 

- 使用 Number() 函数

### 字符串 --> 数字

- 如果是纯数字的字符串, 则将其直接转换为数字.  
- 如果字符串中有非数字的内容, 则转换为NaN.  
- 如果字符串是一个空串, 或者全是空格的, 转换为 0.

```js
a = "123";  
a = Number(a);  
console.log(typeof a);  //number
console.log(a);  // 123

a = "abc";  
a = Number(a);  
console.log(typeof a);  //number
console.log(a);  // NaN

a = "";  
a = Number(a);  
console.log(typeof a);  //number
console.log(a);  // 0

a = "   ";  
a = Number(a);  
console.log(typeof a);  // number
console.log(a);  // 0
```

### 布尔值 --> 数字

- true 转换为 1
- false 转换为 0
- Null --> 转换为数字 0
- Undefined --> 转换为数字 NaN

```js
a = true;  
a = Number(a);  
console.log(typeof a);  // number
console.log(a);  // 1

a = false;  
a = Number(a);  
console.log(typeof a);  // number
console.log(a); // 0

a = null;  
a = Number(a);  
console.log(typeof a);  // number
console.log(a);  // 0

a = undefined;  
a = Number(a);  
console.log(typeof a);  // number
console.log(a);  // NaN
```

## 方法二:

- 这种方式专门用来对付字符串  
- `parseInt()` 把一个字符串转换为一个整数.  
- `parseFlote()` 把一个字符串转换为一个浮点数.

- 调用 `parseInt()` 函数将 `a` 转换为 `Number`
- `parseInt()` 可以将一个字符串中的有效整数取出来,  然后转换为` Int`, 注意数字内容只取从开头数字到第一个非数字之前.  
- 开头是非数字, NaN  
- 中间有非数字, 只取非数字之前的.  
- 数字是小数, 只取整数位.  
 
- parseFloat() 作用和 parseInt() 类似,  
- 不同的是可以获取有效小数.

```js
a = "123px";  
a = parseInt(a);  
console.log(typeof a);  // number
console.log(a);  // 123

a = "123.456px";  
a = parseFloat(a);  
console.log(typeof a);  // number
console.log(a);  // number
```

- 如果对非 `String` 使用 `parseInt()` 或 `parseFloat()`
- 它会先将其转换为 `String` 然后再操作

```js
a = true;  
a = parseInt(a);  
console.log(typeof a);  // number
console.log(a);  // NaN
```