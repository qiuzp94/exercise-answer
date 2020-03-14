# 第 6 题
## 题目
用过 Promise 吗？举例说明。
如果要你创建一个返回 Promise 对象的函数，你会怎么写？举例说明。

## 答案：
### 第一问答案：
用过,Promise第一个意义：完全不用考虑传入的是success还是成功，是error还是fail，直接then一下就可以使用
第二个意义：标准化操作。

### 第二问答案：
``` javascript
window.jQeuery.ajax=function({url,method,body,headers}){
return new Promise(function(resolve,reject){
  
  let request = new XMLHttpRequest()
  request.open(method,url)
  request.onreadystatechange = () =>{
  if(request.readyState === 4){
    if(request.status >= 200 && request.status > 300 ){
      resolve.call(undefined,request.responseText)
    }else if(request.status >= 400 ){
      reject.call(undefined，request)
    }
  }
  }
  request.send(body)
}
})
  
```

## 参考答案
用过 Promise，比如 jQuery 或者 axios 的 AJAX 功能，都返回的是 Promise 对象。

``` javascript
$.ajax({url:'/xxx', method:'get'}).then(success1, error1).then(success2, error2)
```

如果我自己创建 Promise 对象，我会这么写

``` javascript
function asyncMethod(){
    return new Promise(function (resolve, reject){
        setTimeout(function(){
            成功则调用 resolve
            失败则调用 reject
        },3000)
    })
}
```