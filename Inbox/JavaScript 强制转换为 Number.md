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

## 进制之间的转换

- 如果需要表示 16 进制的数字, 需要 `0x` 开头  
- 如果需要表示 8 进制的数字, 需要以 `0` 或 `0o `开头  
- 如果需要表示 2 进制的数字, 需要以 `0b` 开头

```js
var a;  

/* 16进制 */
a = 0x16;  
console.log(a);  
  
/* 8 进制 */
a = 0o70;  
console.log(a);  
  
/* 2 进制 */
a = 0b10;  
console.log(a);

/*像"070"这种字符串, 有些浏览器会当成 8 进制解析, 有的会 10 进制*/  
a = "070";  
/*可以在 parseInt() 中, 传递第二个参数, 来指定数字的进制*/  
a = parseInt(a, 10);  
console.log(typeof a);
```

