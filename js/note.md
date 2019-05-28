1 forEach some区别  条件为true是否可以中断遍历
2 const 声明一个引用类型对象  为什么可以修改
3 304的逻辑判断
4 虚拟DOM理解


所有的这些细节  都可以在MDN上面找到答案。


#### 1  创建指定个数数组的快捷方式
```javascript
 let  arr = (new Date(n)).fill('').map((item, index) => index);
 ```

#### 2  获取一个月的天数
> 原理  利用设置天数参数设置为0时返回上个月的最后一天

```javascript
 function getMonthDay(year, month) {
   return (new Date(year, month, 0)).getDate()
 }
 ```
 
 
 #### 3 给一个数组， 求数组中每个元素出现的次数
 > 思路： 通过对象的key值唯一性， 
 
 ```javascript
  var  arr = [1, 2, 2, 3, 4, 4, 4, 4, 5, 5, 5]
  var res = {}
  arr.forEach(scene => {
      if (!res[item]) {
          res[item] = [item];
      } else {
          res[item].push(item)
      }
  })
 ```
 
 #### 5 解构赋值的应用，默认值为什么无效
 > 当且仅当值为undefined时候才会使用默认值
 
 
 #### 6 实现一个es6字符串模板的功能函数
