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
    
    * v-show ：如果需要频繁切换
     
