---
title: note.obsidian.YAML
date: 06-11-2022_星期日
tags: type/note, category/application/Obsidian, source/video, publisher/简睿学堂
---

[LINK: note.obsidian.YAML](https://youtu.be/gFCTmnwQjoQ)

## YAML tags and aliases

### 什么是 front matter
- 是文档开头用 YAML 编写的关于文档的属性. 

### YAML
- 前后都用三个短横先括起来
- 内容用 key: value  的方式表达.
    - 用于描述文档的属性.

#### YAML tags key
- 在 YAML 里可以直接使用 tags key.
    - 后面的 value 不加 '#' 直接建立标签
    - 但是如果使用 '#' , 因为是特殊字符,表示注释.
        - 所以需要使用双引号扩起来, 
        - 但是如果标签多于 1 个, 则需要用中括号建立数组.

#### YAML aliases key
- 别名
    - 用于文件名的特殊符号无法使用的情况. 
    - 或者其他详细或简单的名称
    - 最好的用法, 是如果有些汉语,英语,丹麦语同意的内容, 就可以用别名来连结. 
        - 例如: 
            - [[Object]]
            - [[Object|objekt]]
            - [[Object|宾语]]
