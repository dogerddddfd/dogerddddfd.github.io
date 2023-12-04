## var, let, const
| 关键字   | 变量提升 | 块级作用域   | 重复声明同名变量 | 重新赋值 |
| -------- | -------- | ------------ | ---------------- | -------- |
| var      | √        | ×            | √                | √        |
| let      | ×        | √            | ×                | √        |
| const    | ×        | √            | ×                | ×        |
| 隐式声明 | ×        | 挂载到window | 重新赋值         | √        |
## 解构赋值
```js
let {name,sex} ={name:"fanfusuzi",sex:"man"};
```
## 模板字符串
```js
`模版字符串：${变量}`
```
## 对象简化
```js
let aaa='bbb'
const obj={aaa}
```
## 箭头函数
无自己的this，arguments


## 函数默认值、（es5）argument、rest
* argument：数组，全部参数
* rest：f(a, b, ...arg)；多余参数

## 拓展运算符 \[...\]

## Symbol、（es11）bigint
* 数据类型：number、boolen、string、Null、undefined、Symbol、bigint（es11）、object（引用数据类型）
* Symbol：不运算
```js
let s = Symbol('aaa')
```
## 迭代器iterator

## 生成器函数
https://blog.csdn.net/qq_40850839/article/details/127950154

## Promise

## 集合Set 、Map
> Set:任何数据类型  
> WeakSet: 只能obj；弱引用  
> Map:键值对；键可以是任何数据类型（obj键只能是字符串）  
> WeakMap：键必须是obj，弱引用（键在其他地方不被引用时即删除）  

> JS 有一种垃圾回收策略叫做引用计数，通俗理解就是声明一个对象后，JS 就会使用一个变量用来保存该对象被使用的次数，如果被使用次数为 0 ，那么 JS 就会销毁该对象，释放内存。

## class
```js
class Child extends Parent{
	constructor(value){
		super(value)
		this.val = value
	}
}
```

## 模块化
```js
//引入
import {} from '' //部分引入
import xxx from '' //重命名全部引入
//暴露
export xxx//暴露多个
export default xxx
```
* CommonJs :Nodejs；`var module=require('model')`
* AMD（异步模块定义）：提前执行依赖，推崇依赖前置
* CMD（同步模块定义）：延迟执行依赖，推崇依赖就近

## （ES7）指数\[\*\*\]
## (ES8) async await