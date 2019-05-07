### Promise

[参考资料](https://segmentfault.com/a/1190000018769508)

promise：是一个构造行数，通过以下方法调用：

    const promise = new promise()
    
Promise构造函数的参数为函数：且该函数的参数仍为2个函数 resolve()、reject()

    const promise = new Promise((resolve, reject) => {
      
    })
    
**纠结点来了——生成的Promise实例的then方法，接收2个参数：均为函数**

* 参数一 === 当前Promise实例的resolve(res)
* 参数二 === 当前Promise实例的reject(err)

        const promise = new Promise((resolve, reject) => {
          setTimeout(() => {  // setTimeout用于模拟异步请求啦
            const num = Math.random()
            if (num > 0.5) {
              resolve('success')
            } else () {
              reject('error')
            }
          }, 1000);
        })
        promise.then(res => {
          console.log(res)
        }, err => {
          console.log(err)
        })
    
catch方法——接收1个参数为函数。

    .catch(err => {})

捕获2种情况下的异常：

1. reject状态：参数===当前Promise实例的reject(err)
2. then方法内部异常
    
Promise 链式调用




### Generator

[资料](https://segmentfault.com/a/1190000016707991)

### asyn 函数

[参考文档](http://es6.ruanyifeng.com/#docs/asyn)
