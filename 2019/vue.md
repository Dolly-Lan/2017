### dispatch原理

https://github.com/ElemeFE/element/blob/dev/src/mixins/emitter.js#L23

### 组件状态更新问题 ？

组件初次加载之后，第二次加载，export default之外的代码不会重新执行 ？

### Vue.$data()中引用类型赋值

需要用深拷贝：
    
    import _ from 'lodash'
    const obj = { a: false }
    
    export default {
      data () {
        return {
          obj: _.cloneDeep(obj)
        }
      },
      methods: {
        test () {
          this.$set(this.obj, 'a', true)
        }
      }
    }
