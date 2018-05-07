### vue2.0 升级 

1. $dispatch和$broadcast替换 [资料](https://blog.csdn.net/xqnode/article/details/60941979)

    $dispatch用this.$bus.$emit

    $broadcast用this.$emit替换

2. events选项被移除

    选项被弃用。事件处理器现在在 created 钩子中被注册
