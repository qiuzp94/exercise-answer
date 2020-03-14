# 第 2 题
## 题目

``` javascript
function Fn(){
    console.log(this)
}
new Fn()
//new Fn() 会执行 Fn，并打印出 this，请问这个 this 有哪些属性？这个 this 的原型有哪些属性？
```

## 答案
这个this就是new创建的新对象.
this(这个新对象)有__protot__属性,它指向fn构造函数的原型即fn.prototype
这个原型(即fn.prototype)有两个属性:

construct :它的值是构造函数fn
`__proto__`: 它指向Object.prototype

