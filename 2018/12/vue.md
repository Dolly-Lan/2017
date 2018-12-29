### 修饰符

#### .stop

阻止事件冒泡

    <div @click="test">
      <a @click.stop="doThis"></a>
    </div>

#### .trim

自动过滤用户输入的首尾空白字符

    <input v-model.trim="msg">
    
#### .prevent

阻止默认事件，常阻止form元素的默认submit事件

    <!-- 提交事件不再重载页面 -->
    <form v-on:submit.prevent="onSubmit"></form>

### render(createElement)

[官方文档](https://cn.vuejs.org/v2/guide/render-function.html)

类似template的编译器

#### createElement参数

[官方文档](https://cn.vuejs.org/v2/guide/render-function.html#createElement-参数)

createElement(tag, data, node) 函数返回VNode（虚拟节点），并非返回真实DOM

其中data参数不仅仅可以通过on来监听时间，还可以使用nativeOn监听原生事件

    // 仅用于组件，用于监听原生事件，而不是组件内部使用
    // `vm.$emit` 触发的事件。
    nativeOn: {
      mouseenter: this.fun1,
      mouseleave: this.fun2
    }

### style的scope属性

[使用问题](https://segmentfault.com/a/1190000012184604#articleHeader10)

[解决办法：深度作用选择器](https://vue-loader.vuejs.org/zh/guide/scoped-css.html#深度作用选择器)

### vue router 

[网络资料](https://segmentfault.com/a/1190000015619977#articleHeader3)

路由导入某个文件时要在文件头部引入具体的某个文件,不能用 resolve => require(['xx.vue'], resolve) 或者 () => import('xx.vue') 这种方式， 这两种方式在axios中引入router时出现循环引用的错误！ throw new Error('Cyclic dependency' + nodeRep)
