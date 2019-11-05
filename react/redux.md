## redux常用第三方工具
- redux-persist  持久化
- redux-orm 处理数据相互之间关联性高
- reselect 处理衍生数据
- normalizr 处理嵌套和相关联的数据结构
- Redux Undo  撤销  


## 理解redux中间件
-  中间件干什么的
>  它其实是在action发起到到达reducer之前调用store的方法做你想做的事情

-  中间件如何实现的
```javaqscript
export default function applyMiddleware(...middlewares) { return (next)  => 

        (reducer, initialState) => { var store = next(reducer, initialState); var dispatch = store.dispatch; var chain = []; var middlewareAPI = {
                getState: store.getState,
                dispatch: (action) => dispatch(action)
              };

              chain = middlewares.map(middleware =>
                            middleware(middlewareAPI));

              dispatch = compose(...chain, store.dispatch); return {
                ...store,
                dispatch
              };
           };
}
```

- [参考](http://cn.redux.js.org//docs/advanced/Middleware.html)
