### MessageChannel

 > 第一次接触这个还是在eht钱包metamask中知道的，最近发现深拷贝也可以用它实现， 顿生兴趣要深入了解一波。

#### MDN定义
> Channel Messaging API的Channel Messaging接口允许我们创建一个新的消息通道，并通过它的两个MessagePort 属性发送数据。大概理解就是这东西会创建一
个消息通道， 在这个消息通道的两端可以互联传递消息， 最精妙的地方还是这个消息通道可以通过postMessage传输，这意味着可以让postMessage传输消息通道到
到两个不同的web worker中，从而通过消息通道两端通信实现两个web worker之间的通信，同理的跨域也可以。

### 基础语法

##### 创建一个消息管道

```javascript
const channel = new MessageChannel();
````

##### 访问消息管道两端

```javascript
channel.port1;
channel.port2;
```
