```javascript
const event = {
  clientList: [],

  // 订阅消息
  /**
   * [listen description]
   * @param  {[String]}   key [绑定订阅的类型]
   * @param  {Function} fn  [description]
   * @return {[type]}       [description]
   */
  listen: function(key, fn) {
    if (!this.clientList[key]) {
      this.clientList[key] = []
    }

    this.clientList[key].push(fn)
  },

  // 发布消息
  trigger: function() {
    const key = Array.prototype.shift.call(arguments)
    const fns = this.clientList[key]

    if (!fns || fns.length === 0) {
      return false
    }

    for (let i = 0, fn; fn = fns[i++];) {
      fn.apply(this, arguments)
    }
  },

  // 取消订阅
  remove: function (key, fn) {
    const fns = this.clientList[key]
    if (!fns) {
      return false
    }
    if (!fn) {
      fns && (fns.length = 0)
    } else {
      for (let l = fns.length - 1; l >= 0; l--) {
        const _fn = fns[l]
        if (_fn === fn) {
          fns.splice(l, 1)
        }
      }
    }
  }
}

//  测试
event.listen('sq80', function(price) {
  console.log(`价格： ${price}`)
})

event.listen('sq88', function(price) {
  console.log(`价格： ${price}`)
})

event.trigger('sq88', 88)
event.trigger('sq80', 80)
```
