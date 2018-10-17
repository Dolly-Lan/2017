### watch

  * immediate:true
  
    watch 的一个特点是，最初绑定的时候是不会执行的，要等到监听对象改变时才执行监听计算，当immediate设置为true时则会立即先去执行handler方法

### 全局API通过$符号来访问

  比如要使用nextTick()API，则使用如下方法
    
      this.$nextTick()
      
### computed mounted watch 顺序
 
 computed > mounted > watch
 
### 使用vue-router会在地址栏自动添加/#/号： http://localhost:8081/#/

    let router = new VueRouter({
      mode: 'history',
      scrollBehavior: function (to, from, savedPosition) {
        return savedPosition || { x: 0, y: 0 }
      },
      routes: []
    )]

  
 
