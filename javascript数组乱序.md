### Fisher-Yates算法

```javascript
const arr = [0, 1, 2, 3, 4];
for (let i = 1; i < arr.length; i++) {
    const random = Math.floor(Math.random() * (i + 1));
    [arr[i], arr[random]] = [arr[random], arr[i]];
}

```

### Math.random

```javascrip

const arr = [0, 1, 2, 3, 4];
arr.sort(() => Math.random() > .5);

```



## 参考

- [如何将一个 JavaScript 数组打乱顺序？ 知乎](https://www.zhihu.com/question/68330851/answer/262111061)
