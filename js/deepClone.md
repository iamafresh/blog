## js 浅拷贝和深拷贝

## js的浅拷贝至拷贝对象的第一层的值， 其他拷贝的只是对象的引用地址  [Object.assign()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Object/assign)
就是一个浅拷贝 等于对对象遍历一次

## 深拷贝和浅拷贝的区别就是深拷贝是递归的遍历对象, 理解这点是实现深拷贝的关键思路， 首先判断是否是对象，是对象的时候还要判断是否是数组

### 最简单的实现方式是JSON.parse(JSON.stringify())  但是这个有缺点  不能处理函数  正则，以及原型链上对象等



- [javascript中的深拷贝和浅拷贝？](https://www.zhihu.com/question/23031215)
