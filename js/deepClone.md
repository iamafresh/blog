## js 浅拷贝和深拷贝

#### 浅拷贝

> js的浅拷贝至拷贝对象的第一层的值， 其他拷贝的只是对象的引用地址  [Object.assign()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/assign)
就是一个浅拷贝 等于对对象遍历一次

#### 深拷贝

> 和浅拷贝的区别就是深拷贝是递归的遍历对象, 理解这点是实现深拷贝的关键思路， 首先判断是否是对象，是对象的时候还要判断是否是数组

#### 实现
1 JSON.parse(JSON.stringify()) 
  > 但是这个有缺点  不能处理函数  正则，以及原型链上对象等


2 手动实现
```javascript
function deepClone(obj) {
  var copy;
// Handle the 3 simple types, and null or undefined
  if (null == obj || "object" != typeof obj) return obj;
// Handle Date
  if (obj instanceof Date) {
    copy = new Date();
copy.setTime(obj.getTime());
return copy;
}

  // Handle Array
  if (obj instanceof Array) {
    copy = [];
for (var i = 0, len = obj.length;
i < len;
i++) {
        copy[i] = deepClone(obj[i]);
}
    return copy;
}

  // Handle Function
  if (obj instanceof Function) {
    copy = function() {
      return obj.apply(this, arguments);
}
    return copy;
}

  // Handle Object
  if (obj instanceof Object) {
      copy = {};
for (var attr in obj) {
          if (obj.hasOwnProperty(attr)) copy[attr] = deepClone(obj[attr]);
}
      return copy;
}

  throw new Error("Unable to copy obj as type isn't supported " + obj.constructor.name);
}



```










- [javascript中的深拷贝和浅拷贝？](https://www.zhihu.com/question/23031215)
- [Javascript的对象拷贝](https://www.zcfy.cc/article/copying-objects-in-javascript)
