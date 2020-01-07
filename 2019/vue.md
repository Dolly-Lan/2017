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

通过空格、回车选择自动添加相关配置，如： babel、eslint、router、store等

#### step4:

    yarn serve
    
### vue-cli 3.0  package.json

    "gitHooks": {
        "pre-commit": "lint-staged"
    }
    
#### vue.config.js

    const PROXY_TARGET = "http://xxx"; // 为后台接口联调环境
    const BASE_URL = process.env.NODE_ENV !== "production" ? "/" : "/init"; // 项目生产环境根目录为/init
    const BASE_API_PATH = "/xxx"; // 项目api根目录

    module.exports = {
      // 配置环境变量BASE_API_PATH，修改环境变量BASE_URL（BASE_URL默认为"/"）
      chainWebpack(config) {
        config.plugin("define").tap(args => {
          Object.assign(args[0]["process.env"], {
            BASE_API_PATH: JSON.stringify(BASE_API_PATH),
            BASE_URL: JSON.stringify(BASE_URL)
          });
          return args;
        });
      }, 
      publicPath: BASE_URL,  //  官方文档：https://cli.vuejs.org/zh/config/#publicpath  默认值为"/"
      devServer: {
        proxy: {
          [BASE_API_PATH]: {
            target: PROXY_TARGET,
            changeOrigin: true,
            ws: false
          }
        }
      },
      // 第三方插件配置
      pluginOptions: {}
    };
    
#### router

    import Vue from "vue";
    import VueRouter from "vue-router";
    import axios from "axios";
    import Store from "@/store/index";
    import Index from "@/views/xx/index.vue"; // 默认模块需一开始就加载

    Vue.use(VueRouter);

    const routes = [
      {
        path: "/",
        redirect: "index"
      },
      {
        path: "/index",
        name: "index",
        component: Index
      },
      {
        path: "/routeB",
        name: "routeB",
        component: () => import("@/views/xxx/Index.vue") // 其他模块按需加载
      }
    ];

    const router = new VueRouter({
      mode: "history",
      base: process.env.BASE_URL,
      routes
    });

    export default router;

    
    
### vue中img标签指定图片路径

https://www.cnblogs.com/lemoncool/p/11284586.html

### v-model指令

#### 原生表单的v-model

语法糖：

* text 和 textarea 元素使用 value 属性和 input 事件；

        <input v-model="value" />
        // 是以下写法的语法糖
        <input :value="value" v-on:input="value = $event.target.value" />
        
         <textarea v-model="value" />
        // 是以下写法的语法糖
        <textarea :value="value" v-on:input="value = $event.target.value" />
    
* checkbox 和 radio 使用 checked 属性和 change 事件；

        <input type="radio" name="test" :value="0" v-model="value" />
        <input type="radio" name="test" :value="1" v-model="value" />
        // 等价于
        <input type="radio" name="test" :value="0" :checked="value === 0"  v-on:change="this.value = $event.target.value;"  />
        <input type="radio" name="test" :value="1" :checked="value === 1" v-on:change="this.value = $event.target.value;"  />

 * select 字段将 value 作为 prop 并将 change 作为事件
 
         <select v-model="value">
            <option>0</option>
            <option>1</option>
            <option>2</option>
          </select>
          // 等价于
          <select :value="value" v-on:change="value = $event.target.value;">
            <option :value="0">0</option>
            <option :value="1">1</option>
            <option :value="2">2</option>
          </select>

#### 自定义组件使用v-model

调用CustomInput组件

    <custom-input v-model="data" />{{value}}  // 等价于 <custom-input :value="data" @input="(value) => { data = value }" />{{data}}
    
定义CustomInput.vue

    <input :value="value" v-on:listeners />
    // script
    export defaults {
     props: ['label', 'value'],
      computed: {
        inputListeners: function () {
          var vm = this
          // `Object.assign` 将所有的对象合并为一个新对象
          return Object.assign({},
            // 我们从父级添加所有的监听器
            this.$listeners,
            // 然后我们添加自定义监听器，
            // 或覆写一些监听器的行为
            {
              // 这里确保组件配合 `v-model` 的工作
              input: function (event) {
               vm.$emit('input', event.target.value)
              }
            }
          )
        }
      }
    }
    
    
    
