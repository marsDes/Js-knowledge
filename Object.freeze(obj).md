# Object.freeze() <br>
方法可以冻结一个对象，冻结指的是不能向这个对象添加新的属性，不能修改其已有属性的值，不能删除已有属性，以及不能修改该对象已有属性的可枚举性、可配置性、可写性。也就是说，这个对象永远是不可变的。该方法返回被冻结的对象

## 语法 Object.freeze(obj)

## 示例
```js
let mars = Object.freeze({name:'mars'})
console.log(mars.name);  //mars
mars.name = 'lilei'
console.log(mars.name); // mars
```
 * 数组冻结分浅冻结跟深冻结
[文档链接](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/freeze)
