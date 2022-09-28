# Promise

## 概述
所谓Promise，简单说就是一个容器，里面保存着某个未来才会结束的事件（通常是一个异步操作）的结果。

## 语法
```JavaScript
new Promise(executor);
new Promise(function(resolve, reject) { ... });
```
## 实例

```JavaScript
  let t = 0;
  function testPromise(){
    let times = ++ t;
    console.log(`第 ${times} 次 开始同步代码`)
    let p = new Promise(function(resolve,reject){
      console.log(`第 ${times} 次 开始异步代码`);
      setTimeout(function(){
        resolve(times);
      },3000)
    });
    p.then(function(val){
      console.log(`第 ${val} 次 结束异步代码`)
    });
      console.log(`第 ${times} 次 结束同步代码`)
  }
```
## 资料
https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Promise
