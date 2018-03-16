### $watch

[文档](https://cn.vuejs.org/v2/api/?#vm-watch)

deep选项：

> 为了发现对象内部值的变化，可以在选项参数中指定 deep: true 。注意监听数组的变动不需要这么做

    <button @click="change">change</button>
    data () {
      return {
        obj: {
          'a': 1,
          'b': 2
        }
      }
    },
    watch: {
      obj: {
        handler(newVal){
            alert(newVal.a)
        },
        deep: true
      }
    },
    methods: {
        change () {
            this.obj.a = Math.random()
        }
    }

### v-if 
