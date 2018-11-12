### $bus

$bus.$on(name)——$bus.$off(name)：必须为1对1

  a组件
  
    $bus.$emit(name) // 当$emit的时候，生成了名称为name的事件队列
  
  b组件
  
    $bus.$on(name, fn)   // 当$on监听时，在name的事件队列中添加key值为fn的唯一属性
    $bus.$off(nam, fn)    // 当$off解绑监听，如果第二个参数传了fn，则清除key值为fn的监听，如果不传第二个参数，则把这个name的事件队列全清了
  
