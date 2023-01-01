---
title: JavaScript 变量
date: 27-12-2022
tags: 
aliases: Variable, 变量
---

# JavaScript 变量

- [[JavaScript 变量|变量]]可以用来保存[[JavaScript 字面量]], 而且变量的值是可以任意改变的.    
- 变量更加方便我们直接使用, 所以在开发中推荐通过变量去保存一个字面量, 而很少直接使用字面量.    


### 声明变量 (Declare variables)  
  
- 在 JS 中使用 `var` *关键字* (Key Word) 来*声明* (Declare) 一个**全局变量 (Global Variable)**.  
- 在 JS 中使用 `let` *关键字*来*声明*一个**局部变量 (Local Variable)**.  
- 在 JS 中使用 `const` *关键字*来*声明*一个**常量 (Constant Variable)**.  
  
```js  
var a; let b; const c;  
```  
  
### 变量赋值 (Initialized variables)  
  
- 使用**赋值符号`=`来给变量赋值.  

```js  
a = 123; a = 456; a = 12312312313;
```
- 可以同时对变量进行声明和赋值.  

```js  
var b = 789; var c = 0;  
```

- 可以通过变量对字面量进行描述  

```js  
var age = 30;
```
