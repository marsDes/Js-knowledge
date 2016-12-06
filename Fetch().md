#Fetch
##概述
fetch方法用于发起获取资源的请求。它返回一个 promise，这个 promise 会在请求响应后被 resolve，并传回 Response 对象。
##语法
```javascript
fetch(input, init).then(function(response) { ... });
```
##参数
input
定义要获取的资源。这可能是：
>一个 USVString 字符串，包含要获取资源的 URL。
>一个 Request 对象。
init(可选)
一个配置项对象，包括所有对请求的设置。可选的参数有：
>method: 请求使用的方法，如 GET、POST。
>headers: 请求的头信息，形式为 Headers 对象或 ByteString。
>body: 请求的 body 信息：可能是一个 Blob、BufferSource、FormData、URLSearchParams 或者 USVString 对象。
       注意 GET 或 HEAD 方法的请求不能包含 body 信息。
##实例1
```javascript
var myImage = document.querySelector('img');

var myRequest = new Request('flowers.jpg');

fetch(myRequest).then(function(response) {
  return response.blob();
}).then(function(response) {
  var objectURL = URL.createObjectURL(response);
  myImage.src = objectURL;
});
```
##实例2（带init配置项)
```javascript
var myImage = document.querySelector('img');

var myHeaders = new Headers();
myHeaders.append('Content-Type', 'image/jpeg');

var myInit = { method: 'GET',
               headers: myHeaders,
               mode: 'cors',
               cache: 'default' };

var myRequest = new Request('flowers.jpg');

fetch(myRequest,myInit).then(function(response) {
  ... 
});
```
##资料
https://developer.mozilla.org/zh-CN/docs/Web/API/GlobalFetch/fetch
