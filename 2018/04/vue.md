### vuex 

[官方文档](https://cn.vuejs.org/v2/guide/state-management.html#%E7%AE%80%E5%8D%95%E7%8A%B6%E6%80%81%E7%AE%A1%E7%90%86%E8%B5%B7%E6%AD%A5%E4%BD%BF%E7%94%A8)

> 组件不允许直接修改属于 store 实例的 state，而应执行 action 来分发 (dispatch) 事件通知 store 去改变，我们最终达成了 Flux 架构。这样约定的好处是，我们能够记录所有 store 中发生的 state 改变，同时实现能做到记录变更 (mutation)、保存状态快照、历史回滚/时光旅行的先进的调试工具。


    store |-- state   ( menus )
          |-- action  ( store.dispatch('SET_HEADER_MENUS_ACTION',menus) )
          |-- mutation ( function SET_HEADER_MENUS_ACTION(state,menus){state.menuState.menus = menus} )


### 升级vue2踩坑

 1. ready() 替换成 mounted()
 
 2. 

