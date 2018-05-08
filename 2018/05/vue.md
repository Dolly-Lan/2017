### vue2.0 升级 

1. $dispatch和$broadcast替换 [资料](https://blog.csdn.net/xqnode/article/details/60941979)

    $dispatch用this.$bus.$emit

    $broadcast用this.$emit替换

2. events选项被移除

    选项被弃用。事件处理器现在在 created 钩子中被注册
    
3. v-for 遍历数组时的参数顺序 变更 

    [官方文档](https://cn.vuejs.org/v2/guide/migration.html#ready-%E6%9B%BF%E6%8D%A2)
    
    (index, value)变成(value, index)

4. route的activate钩子替换beforeRouteEnter 

    [官方文档](https://segmentfault.com/q/1010000008973485/a-1020000008978129)
    [资料](https://segmentfault.com/q/1010000008973485/a-1020000008978129)

5. 控制台报错[vue-router] Named Route 'home' has a default child route  

    [资料](https://www.licoy.cn/2964.html)
    
### vuex

1. [vue1.x源码示例](https://github.com/vuejs/vuex/tree/dev/examples/shopping-cart)

2. [vue2.x源码示例子](https://github.com/vuejs/vuex/tree/master/examples/counter-hot)

3. state和getters

    state: 在计算属性中返回某个状态
    
        computed: {
          count: function () {
            return store.state.count
          }
        }
    
    getters: 该 getter 函数将会把仓库的 `store.state.count` 绑定为组件的 `this.count`
    
        export default {
          template: '...',
          data () { ... },
          // 此处为我们从 store 实例中取回状态的位置
          vuex: {
            getters: {
              // 该 getter 函数将会把仓库的 `store.state.count` 绑定为组件的 `this.count`
              count: function (state) {
                return state.count
              }
            }
          }
        }

    
