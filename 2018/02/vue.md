### 全局 API

1. Vue.component( id, [definition])：注册或获取全局组件

        Vue.component(id, vue对象)  // 注册
        var MyComponent = Vue.component('my-component')  // 获取
    
    
### render函数v-model

render 函数中没有与 v-model 相应的 api - 你必须自己来实现相应的逻辑：

    render: function (createElement) {
      var self = this
      return createElement('input', {
        domProps: {
          value: self.value
        },
        on: {
          input: function (event) {
            self.value = event.target.value
            self.$emit('input', event.target.value)
          }
        }
      })
    }

