### 中断请求

[文档](http://www.axios-js.com/zh-cn/docs/#%E5%8F%96%E6%B6%88)

以vue项目为例

切换路由中断所有请求： 可以使用同一个token取消多个请求，使用router + store

    // router/index.js
    import axios from "axios";
    import Store from "@/store/index";
    
    router.beforeEach((to, from, next) => {
      cancelRequest();
      next();
    });

    function cancelRequest() {
      Store.state.source &&
        Store.state.source.cancel &&
        Store.state.source.cancel(); // 取消上一次请求
      Store.state.source = axios.CancelToken.source(); // 更新source： 调用axios.CancelToken.source()方法，返回{ token, cancle() }
    }
    
    // http.js
    import axios from "axios";
    import Store from "@/store/index";
    
    http.interceptors.request.use(
      function(config) {
        // Do something before request is sent
        config.cancelToken = Store.state.source.token; // 给当前页所有请求config添加cancelToken字段，值为最新的axios.CancelToken.source().token
        return config;
      },
      function(error) {
        // Do something with request error
        return Promise.reject(error);
      }
    );
    
    // store/source.js
    export default {
      namespaced: true,
      state: {
        token: null,
        cancel: null
      },
      // getters
      getters: {},

      // actions
      actions: {},

      // mutations
      mutations: {}
    };
