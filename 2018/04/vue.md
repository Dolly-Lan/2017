### vuex 

[官方文档](https://cn.vuejs.org/v2/guide/state-management.html#%E7%AE%80%E5%8D%95%E7%8A%B6%E6%80%81%E7%AE%A1%E7%90%86%E8%B5%B7%E6%AD%A5%E4%BD%BF%E7%94%A8)

> 组件不允许直接修改属于 store 实例的 state，而应执行 action 来分发 (dispatch) 事件通知 store 去改变，我们最终达成了 Flux 架构。这样约定的好处是，我们能够记录所有 store 中发生的 state 改变，同时实现能做到记录变更 (mutation)、保存状态快照、历史回滚/时光旅行的先进的调试工具。


    store |-- state   ( menus )
          |-- action  ( store.dispatch('SET_HEADER_MENUS_ACTION',menus) )
          |-- mutation ( function SET_HEADER_MENUS_ACTION(state,menus){state.menuState.menus = menus} )
          
  vuex 1.0 [代码示例](https://github.com/vuejs/vuex/tree/master/examples/counter-hot)
  
  vuex 2.0 [代码示例](https://github.com/vuejs/vuex/tree/dev/examples/shopping-cart)


### 升级vue2踩坑

 1. ready() 替换成 mounted()
 
 2. v-el: elName 替换成 ref="elName"

 3. v-link指令 替换成 <router-link>组件 [官方文档](https://cn.vuejs.org/v2/guide/migration-vue-router.html#v-link-%E6%9B%BF%E6%8D%A2)
 
 4. router.go()限定用途 只用作“前进/后退” 如果用做“导向特殊页面”必须使用router.push() [官方文档](https://cn.vuejs.org/v2/guide/migration-vue-router.html#router-go-%E6%94%B9%E5%8F%98)
 
 5. vuex 0.6+ 需升级到 vuex 0.8+ [官方文档](https://cn.vuejs.org/v2/guide/migration.html#FAQ) 
    
> 对于 Vuex ，版本 0.8+ 与 Vue 2 保持兼容，所以部分不必强制升级。
    
 5. vue Router  [官方文档](https://cn.vuejs.org/v2/guide/migration.html#FAQ)
    
> Vue Router 2 与 Vue 2 保持兼容，所以 Vue Router 是需要升级的，你必须遵循 [Vue Router 迁移方式](https://cn.vuejs.org/v2/guide/migration-vue-router.html)来处理
