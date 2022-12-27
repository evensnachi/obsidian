---
title: 标识符
date: 27-12-2022
tags: 
aliases: JS标识符, Identifier, JS Identifier, 
---

# 标识符

- 在 JS 中所有可以自主命名的都可以称为标识符.  
- 例如: 变量名, 函数名, 属性名.


#### 标识符命名规则  
  
1. 标识符中只能还有**字母,数字,下划线,美元符**.  
2. 标识符不能以数字开头.  
3. 标识符不能是 js 中的关键字或保留字.  
4. 标识符一般使用驼峰命名法.  
  
例如:  
```js  
variableName; 
functionName(); 
(attributeName : attribute); 
ConstantName; 
InterfaceName{}; 
<GeneraterName>  
```

- js 底层保存的标识符,实际上采用的是 Unicode 编码, 所以理论上来说,   所有的 utf-8 中含有的内容都可以作为标识符. 所以中文实际上是可以使用作为标识符的.  
- ** 但是千万不要用!!!**