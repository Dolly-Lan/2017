### vue2.0 升级 

1. $dispatch和$broadcast替换 [资料](https://blog.csdn.net/xqnode/article/details/60941979)

    $dispatch用this.$bus.$emit

    $broadcast用this.$emit替换

2. events选项被移除

    选项被弃用。事件处理器现在在 created 钩子中被注册
    
3. v-for 遍历数组时的参数顺序 变更 https://cn.vuejs.org/v2/guide/migration.html#ready-%E6%9B%BF%E6%8D%A2

4. beforeRouteEnter https://segmentfault.com/q/1010000008973485/a-1020000008978129

5. 控制台报错[vue-router] Named Route 'home' has a default child route  https://www.licoy.cn/2964.html
