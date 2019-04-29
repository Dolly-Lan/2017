### $refs

[官方资料](https://cn.vuejs.org/v2/api/#ref)

> 关于 ref 注册时间的重要说明：因为 ref 本身是作为渲染结果被创建的，在初始渲染的时候你不能访问它们 - 它们还不存在！$refs 也不是响应式的，因此你不应该试图用它在模板中做数据绑定。

1. 在初始渲染的时候你不能访问它们：此时{{$refs.child.name}}会产生报错，因为$refs此时无法访问

        <div>
          <child ref='child'></child>  <!--假设child组件中有一个为name的data-->
          <div>{{$refs.child.name}}</div>
        </div>
      
### $route.push() 中query 和 params参数的区别

相同：都可以用于通过url传递参数

不同： query相当与get请求，post相当于post请求：因此通过query传递的参数会添加在url上，通过params则不会

