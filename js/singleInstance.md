# 单例模式

/**
  Question 5: please create a tool to generate Sequence
  Expected to be used like:
  var sequence1 = new Sequence();
  sequence1.next() --> return 1;
  sequence1.next() --> return 2;
  
  in another module:
  var sequence2 = new Sequence();
  sequence2.next() --> 3;
  sequence2.next() --> 4;
**/


```javasript
function Sequence() {
  if (Sequence.instance !== undefined) {
    return Sequence.instance
  }

  this.count = 0
  this.next = function () {
    return ++this.count
  }
  Sequence.instance = this
}
```



- 最近这个面试题才让我真正的理解单例模式的用途


-[单例模式](https://www.cnblogs.com/chris-oil/p/4092865.html )
