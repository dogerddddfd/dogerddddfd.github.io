### vue2与vue3
> 监测机制,响应式原理
> 
> 数据和方法的定义: Vue2使⽤的是选项类型API（Options API），Vue3使⽤的是组合式API（Composition API） 
> 分割、可读性
>
> 生命周期钩子

| vue2          | vue3            | 说明                        |
| ------------- | --------------- | --------------------------- |
| beforeCreate  | setup()         | 组件创建之前                |
| created       | setup()         | 组件创建完成                |
| beforeMount   | onBeforeMount   | 组件挂载之前                |
| mounted       | onMounted       | 组件挂载完成                |
| beforeUpdate  | onBeforeUpdate  | 数据更新，虚拟DOM打补丁之前 |
| updated       | onUpdated       | 数据更新，虚拟DOM渲染完成   |
| beforeDestroy | onBeforeUnmount | 组件销毁之前                |
| destroyed     | onUnmounted     | 组件销毁后                  |
| activated     | onActivated     |
| deactivated   | onDeactivated   |

若组件被<keep-alive>包含，则多出下面两个钩子函数。  
onActivated(): 被包含在中的组件，会多出两个生命周期钩子函数。被激活时执行 。  
onDeactivated(): 比如从 A组件，切换到 B 组件，A 组件消失时执行。