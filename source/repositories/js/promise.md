## api
> pending: 初始状态, 初始状态，未完成或拒绝。  
> fulfilled: 意味着操作成功完成。  
> rejected: 意味着操作失败  
* 使用
```js
new Promise((resolve,reject)=>{
	resolve('success');
	//或者
	reject('error')
}).then(result=>{
	console.log('success')
}).catch(error=>{
	console.log('error')
}).finally(()=>{
	console.log('end')
})
```
* Promise.resolve(): 将现有对象转为 Promise 对象
> thenable对象: 转为 Promise 对象  
> > 无then方法的对象，或不是对象:  
> > 返回一个新的 Promise 对象，状态为resolved。  
> > 无参数：直接返回一个resolved状态的 Promise 对象。  
* Promise.all(\[promise数组\]) :全部成功，返回成功promise；否则失败
```js
Promise.all([promise1,promise1]).then(res=>{
	console.log('全部完成，fulfilled')
}).catch(rea=>{
	console.log('有失败，rejected')
})
```
* `Promise.race([promise数组])` :返回一个promise，状态由第一个成功返回的promise的状态决定
* ` Promise.any([promise数组]) `：有一个成功，返回成功promise；都不成功，返回失败
* `Promise.allSettled([promise数组]) `：全部成功后，进入then回档(只进入then)


## 手写Promise.All
```js
Promise.myall = function (pmarr) {
  // 手写Promise.all最终返回的还是一个promise,所以我们创建一个promise并返回
  return new Promise((resolve, reject) => {
    try {
      /**
     * 首先要判断迭代器的个数
     * 但是这里不能用length的方式去判断,因为它可能不是一个数组,也限定必须是数组
     * 要用循环的方式去判断,一定要用forin 因为它不一定是数组可能是对象
     * 
     * 如果你考虑严谨一点的话,可以对pmarr进行一些校验 如下
    */
      if (pmarr === undefined) reject('没有迭代器')
      let length = 0 // 记录迭代器的个数
      let resultLength = 0// 记录已执行的promise个数
      let result = [] // 用于存储返回暑假
      for (const key in pmarr) {
        length++
        /**
         * 1因为item不一定都是promise对象,所以要全部转一下,
         * 2因为每个promise成功或者是失败都有回调,所以我们要去拿到每一个prmoise的返回状态
         * 3拿到每一个prmise的返回状态后不能用push的方式添加到result中,返回结果的顺序需要和pmarr的顺序一致
         * 4当其中有一项prmise返回的失败则整个promise.all就会返回失败,所以直接reject放在第二个参数中,
         *    只要失败一个并返回失败终止循环
         * 5判断迭代器是否都执行完,全部执行完后返回成功
        */
        Promise.resolve(pmarr[key]).then(res => {
          result[key] = res
          resultLength++
          if (length === resultLength) resolve(result)
        }, reject)
      }
      // 当没有转入迭代器时直接返回成功状态
      if (!length) resolve([])
    } catch (error) {
      reject(error)
    }
  })
}

// 输出[1,2]
Promise.myall([fun1(),fun2()]).then(res=>{
  console.log(res);
})


```
## async await
* promise语法糖
* es8
```js
async function f(){
	f_1()
	await f_2()
	f_3()
}

//相当于
new Promise((resolve,reject)=>{
	f_1()
	resolve(f_2())
}).then(res=>{
	f_3()
})
``` 