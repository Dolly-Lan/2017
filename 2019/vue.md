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

### Vue-cli 3.0 构建项目

[文档](https://cli.vuejs.org/zh/guide/prototyping.html)

#### step1:

    yarn add global @vue/cli  //npm i @vue/cli -g
    
升级vue-cli可能会遇到问题，请参考资料：[资料](https://blog.csdn.net/inthat/article/details/90268110)
    
>vue cli 的包名称由 vue-cli 改成了 @vue/cli。 如果你已经全局安装了旧版本的 vue-cli (1.x 或 2.x)，你需要先通过 npm uninstall vue-cli -g 或 yarn global remove vue-cli 卸载它。然后安装新的

#### step2:

    vue create vue-test
    
#### step3:

一路回车

#### step4:

    yarn serve
    
### vue-cli 3.0  package.json

    "gitHooks": {
        "pre-commit": "lint-staged"
    },
