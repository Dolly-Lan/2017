### $watch

[文档](https://cn.vuejs.org/v2/api/?#vm-watch)

deep选项：

> 为了发现对象内部值的变化，可以在选项参数中指定 deep: true 。注意监听数组的变动不需要这么做

    <button @click="change">change</button>
    data () {
      return {
        obj: {
          'a': 1,
          'b': 2
        }
      }
    },
    watch: {
      obj: {
        handler(newVal){
            alert(newVal.a)
        },
        deep: true
      }
    },
    methods: {
        change () {
            this.obj.a = Math.random()
        }
    }

### v-if 和 v-show 的区别 

[参考资料](http://www.cnblogs.com/DCL1314/p/8135502.html)

1. 从DOM的角度来说：

    *  v-if是动态的向DOM树内添加或者删除DOM元素

    *  v-show是通过设置DOM元素的display样式属性控制显隐

2. 从vueJS编译角度：

    *  v-if是惰性的 ：如果在初始渲染时条件为假，则什么也不做;在条件第一次变为真时才开始局部编译（编译会被缓存起来）;在切换 v-if 块时，Vue.js 有一个      局部编译/卸载过程，因为 v-if 之中的模板也可能包括数据绑定或子组件，它会确保条件块在切换当中合适地销毁与重建条件块内的事件监听器和子组件。
    
    *  v-show是在任何条件下（首次条件是否为真）都被编译，然后被缓存，而且DOM元素保留
    
3. 从性能消耗的角度

    *  v-if有更高的切换消耗，
    
    *  v-show有更高的初始渲染消耗
    
4. 从使用场景角度

    *  v-if：如果在运行时条件不大可能改变，且内部包含不需要watch父组件传过来的props的组件
    
    *  v-show ：如果需要频繁切换
    
### $options **只读**

    > 获取Vue实例的初始化选项

### 生命周期

  1. created: 在实例创建完成后被立即调用,实例已完成以下的配置：数据观测 (data observer)，属性和方法的运算，watch/event 事件回调。然而，挂载阶段还没开始
  
  2. mounted: 子组件开始挂载在$el上。 注意 mounted 不会承诺所有的子组件也都一起被挂载。如果你希望等到整个视图都渲染完毕，可以用 vm.$nextTick 替换掉 mounted：
  
    mounted: function () {
      this.$nextTick(function () {
        // Code that will run only after the
        // entire view has been rendered
      })
    }
    
  3. beforeDestroy：实例销毁之前调用。
  
    应用场景举例: mounted周期中调用定时器，可以在beforeDestroy中清除
    
### $emit/$on

on和emit的事件必须是在一个公共的实例上，才能触发。

> vm.$on( event, callback ) 监听当前实例上的自定义事件。事件可以由vm.$emit触发。回调函数会接收所有传入事件触发函数的额外参数。

> vm.$emit( event, […args] ) 触发当前实例上的事件。附加参数都会传给监听器回调。

### vue子组件向父组件通信

[官方文档](https://cn.vuejs.org/v2/guide/migration.html#events-%E9%80%89%E9%A1%B9-%E7%A7%BB%E9%99%A4)

1. event hub [参考](https://blog.csdn.net/baidu_31333625/article/details/74928608)

2. @/v-on 监听子组件上 $emit 的变化

3. .sync

    // 父组件
    <div style=><child v-bind::width.sync="value"></child></div>
    
    // 子组件
    <button @click='change'>修改宽度</button>
    props: {
      width: Number
    },
    methods: {
      change () {
        this.$emit('update:width': 100)
      }
    }
    
    

     
