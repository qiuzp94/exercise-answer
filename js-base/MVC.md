# 第 4 题
## 题目
前端 MVC 是什么？
请用代码大概说明 MVC 三个对象分别有哪些重要属性和方法。

## 答案
### 前端 MVC 是什么？
MVC就是一种编程思想,将代码分为三个模块
    * M:Model 模式  作用操作数据，操作(初始化，获取，保存)
    * V:View 视图   作用是告诉js，页面中的哪些代码块是我这个模块对应的东西
    * C:Controller 控制器   作用是负责其他所有的事情，一个Controller事件只操作一个事件。
    * 总的来说，V就是视图，M是数据，所有相关数据的操作都应该放在model里面，Controll是控制器，它来控制其他所有的代码。MVC是一种代码组织形式。它不是任何一种框架，也不是任何一种技术。
它就是一种组织代码的思想。



### 请用代码大概说明 MVC 三个对象分别有哪些重要属性和方法。

``` javascript
window.Model = function (options) {
    let resourceName = options.resourceName
    return {
        init: function () {},
        fetch: function () {},
        save: function (object) {}
    }
}

window.View = function(selector){
    return document.querySelector(selector)
}

window.Controller = function (options) {
    var init = options.init
    let object =  {
        view: null,
        model: null,
        init: function (view, model) {
            this.view = view
            this.model = model
            this.model.init()
            init.call(this, view, model)
            this.bindEvents.call(this)
        },
    }
   
    for (let key in options) {
        if (key !== 'init') {
            object[key] = options[key]
        }
    }
    return object

}


```

### 参考答案

MVC 是什么
MVC 是一种设计模式（或者软件架构），把系统分为三层：Model数据、View视图和Controller控制器。
Model 负责数据管理，包括数据逻辑、数据请求、数据存储等功能。前端 Model 主要负责 AJAX 请求或者 LocalStorage 存储
View 负责用户界面，前端 View 主要负责 HTML 渲染。
Controller 负责处理 View 的事件，并更新 Model；也负责监听 Model 的变化，并更新 View，Controller 控制其他的所有流程。
代码说明

``` javascript
var model = {     
    data: null,    
    init(){}    
    fetch(){}     
    save(){}    
    update(){}    
    delete(){}
 } 
view = {    
     init() {}     
     template: '<h1>hi</h1>'
 } 
controller = {   
     view: null,     
     model: null,     
     init(view, model){ 
         this.view = view       
         this.model = model 
         this.bindEvents()    
 }    
     render(){         
          this.view.querySelector('name').innerText = this.model.data.name     
},    
     bindEvents(){} 
}
``` 