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

### async 函数

[参考文档](http://es6.ruanyifeng.com/#docs/async)

> 进一步说，async函数完全可以看作多个异步操作，包装成的一个 Promise 对象，而await命令就是内部then命令的语法糖。

async表示函数里有异步操作，返回Promise对象

    async function getData () {
        return await asyncData()  // 假设asyncData为异步函数
    }
    getData().then().catch()

await中断函数

1. 表示中断函数，如果是Promise对象，则直到await后面的异步操作resolve，才会返回新的Promise对象，然后继续执行后面的代码
2. 如果await后面的异步操作reject，则中断整个函数的执行

    asyncData () {
        return new Promise((resolve, reject) => {
          setTimeout(() => {
            resolve('success')
          }, 3000)
        })
    },
    let data = ''
    async function getData () {
        data = await asyncData()
        console.log(data)
    }
    
异常处理：

await:

1. try...catch...处理await

        asyncData () {
            return new Promise((resolve, reject) => {
              setTimeout(() => {
                reject('err')
              }, 3000)
            })
        },
        let data = ''
        async function getData () {
            try {
                data = await asyncData()
            } catch(err) => {
                console.log(err)
            }
        }
        getData()  // 'err'
        
2. wait后面使用catch函数捕获异常
    
        asyncData () {
            return new Promise((resolve, reject) => {
              setTimeout(() => {
                reject('err')
              }, 3000)
            })
        },
        let data = ''
        async function getData () {
            data = await asyncData().catch(err => { console.log(err) })
        }
        getData()  // 'err'

async:

    async function getData () {
        return await asyncData()  // 假设asyncData为异步函数
    }
    getData().then(res => {
        // 假设asyncData resolve，则return asyncData的Promise对象
    }).catch(err => {
        // 假设asyncData reject，则return asyncData的Promise对象
    })
    
注意：当async无论有没有return，一旦await后的Promise被reject，async的catch会捕获到reject

    async function getData () {
        await asyncData()  // 假设asyncData为异步函数
    }
    getData().catch(err => {
        
    })
    
补充： 当一个async中有多个并发请求时：

### String.includes(string)

判断字符串中是否包含目标字符串，返回true/false

### reduce会影响initValu(Obj类型)

    const b = [1, 2, 3]
    undefined
    b.reduce((cur, prev) => {cur[prev] = 1; return cur}, a);
    {1: 1, 2: 1, 3: 1}
    a
    {1: 1, 2: 1, 3: 1}
    const c = 0;
    undefined
    b.reduce((cur, prev) => {return cur += prev}, c);
    6
    c
    0
