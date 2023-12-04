## query,params
* query刷新不会丢失query里面的数据 params刷新会丢失 params里面的数据。
* query:
-  url: `......?aaa=1&bbb=2`  
-  vue.\$router.push({path,query})  
-  vue.\$route.query.aaa  

* params
- url: 可不显示参数
- 		....../1/name
- vue.$router.push({path,params})
- vue.$route.params.name

## 配置用法
```js
const routes =[
    {path:"路径",component:"组件",redirect:'重定向',
        children:[]
    }
]
```

## \$router 和 \$route
* this.$router  全局的路由对象
* this.$route  本页面的路由对象

## 路由模式
* Hash 模式：
    * history: createWebHashHistory(),
    * 地址改变时通过 hashchange 事件，只会读取哈希符号后的内容，并不会发起任何网络请求。
    *  地址中永远带着#
* history 模式：
    * history: createWebHistory(),
    * 每访问一个页面都要发起网络请求
    * 无#
    * 怕刷新, 应该返回同一个 `index.html` 页面

## 路由守卫
https://router.vuejs.org/zh/guide/advanced/navigation-guards.html