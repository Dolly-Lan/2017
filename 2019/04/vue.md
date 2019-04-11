### $refs

[官方资料](https://cn.vuejs.org/v2/api/#ref)

> 关于 ref 注册时间的重要说明：因为 ref 本身是作为渲染结果被创建的，在初始渲染的时候你不能访问它们 - 它们还不存在！$refs 也不是响应式的，因此你不应该试图用它在模板中做数据绑定。

1. 在初始渲染的时候你不能访问它们

      <div>
        <child ref='child'></child>
      </div>
      

