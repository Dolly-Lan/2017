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

### vue开发规范

[官方资料](https://cn.vuejs.org/v2/style-guide/)

### data

必须要用函数声明data，由于data return {} 一个对象，为引用类型，则这个组件的所有实例之间共享这个data，因此必须使用data()来生成一个新的对象。

    data() {
        return {}
    }

### Vue-cli 3.0

[文档](https://cli.vuejs.org/zh/guide/prototyping.html)

#### step1:

    npm i @vue/cli -g

#### step2:

    vue create vue-test
