### 1. for  in
> for in 遍历遍历对象自生和从原型链继承来的可枚举属性

```javascript
const person = {}
person.__proto__ = {name: 'song'}

for (var props in person) {
  console.log(props)   // name
}

```

### 2. Object.keys() or Object.values()
> 遍历对象自身所有可枚举属性, 不可枚举属性不能被遍历

```javascript
const person = {name: 'xxx'}
Object.defineProperty(person, 'age', {value: 120, enumerable: false})

Object.keys(person)  // ["name"]
```

### 3. Object.getOwnPropertyNames()
> 遍历对象自身的所有属性， 包括不可枚举属性

```javascript
const person = {name: 'xxx'}
Object.defineProperty(person, 'age', {value: 120, enumerable: false})

Object.getOwnPropertyNames(person)  // ["name", "age"]
```

### 4. Reflect.ownKeys()
> 返回对象自身所有属性以及包括symbol类型作为key 的属性

```javascript
const sym = Symbol.for('id')
const person = {[sym]: '001', name: 'xxx'}
Object.defineProperty(person, 'age', {value: 120, enumerable: false})


Reflect.ownKeys(person)  // ["name", "age", Symbol(id)]
```

### 总结
> 遍历javaScript对象有多种方法，需要根据不用的需求选择方法
  - 遍历对象自身所有属性， 那就用Object.getOwnPropertyNames()
  - 遍历对象自身可枚举属性， 用Object.keys()
  - 遍历symbol类型的作为key的属性， 用Reflect.ownKeys()
  - 遍历对象自身和继承属性， 那就for ... in 


### 参考
- [Reflect.ownKeys()](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Reflect/ownKeys)
