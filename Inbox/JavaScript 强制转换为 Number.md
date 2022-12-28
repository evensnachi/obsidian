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
console.log(typeof a);  
console.log(a);
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
console.log(typeof a);  
console.log(a);

a = "abc";  
a = Number(a);  
console.log(typeof a);  
console.log(a);

a = "";  
a = Number(a);  
console.log(typeof a);  
console.log(a);

a = "   ";  
a = Number(a);  
console.log(typeof a);  
console.log(a);
```

### 布尔值 --> 数字

- true 转换为 1
- false 转换为 0
- Null --> 转换为数字 0
- Undefined --> 转换为数字 NaN

## 方法二:

- 这种方式专门用来对付字符串  
- `parseInt()` 把一个字符串转换为一个整数.  
- `parseFlote()` 把一个字符串转换为一个浮点数.