## 第 3 题
## 题目
JSON 和 JavaScript 是什么关系？JSON 和 JavaScript 的区别有哪些？

## 答案：
### JSON 和 JavaScript 是什么关系？
JSON是基于JavaScript是一个子集，同时也是一种数据交互格式。

### JSON 和 JavaScript 的区别有哪些？
JSON 中的字符串必须用双引号括起，JavaScript 中字符串单双引号都可以；
JSON 中没有变量，所以不能引用，JavaScript中有变量，可以引用；
JSON 中没有原型链，JavaScript有原型链；


## 参考答案
关系：JSON 是一门抄袭/借鉴 JavaScript 的语言，同时也是一种数据交互格式，JSON 是 JavaScript 的子集（或者说 JSON 只抄袭了一部分 JavaScript 语法，而且没有新增任何原创的语法）
区别：JSON 不支持函数、undefined、变量、引用、单引号字符串、对象的key不支持单引号也不支持不加引号、没有内置的 Date、Math、RegExp 等。
而 JavaScript 全都支持。

