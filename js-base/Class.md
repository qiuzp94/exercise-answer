# 第 5 题
## 题目 
在 ES5 中如何用函数模拟一个类？
提示：这是一个开放题，请自己想一个好的例子，然后用代码来阐述你的观点。

## 答案
在 ES5 中可以用构造函数法、Object.create()法、封装、继承、私有属性和私有方法、数据共享来模拟一个类

构造函数法 在其内部用 this 关键字指代实例对象。
``` javascript
function Obj(a, b){
  this.a = a;
  this.b = b;
}
//把那些不变的属性和方法，直接定义在prototype对象上
Obj.prototype.text = "hello world"

// 生成实例的时候，使用new关键字。
var obj = new Obj(1, 2); //obj 等价于 { a:1, b:2 }

obj.text  //"hello world"
```


## 参考答案
ES 5 没有 class 关键字，所以只能使用函数来模拟类。
``` javascript
function Human(name){
    this.name = name
}
Human.prototype.run = function(){}

var person = new Human('frank')
```