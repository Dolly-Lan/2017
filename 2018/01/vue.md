### 生命周期

1. created 不会去更新当前props值 优先于mounted
2. mounted 也不会去更新当前props的值
3. destroy

### 指令

1. v-html 在dom中嵌入渲染包含html代码的变量

### 修饰符

1. .native  给vue组件绑定原生的事件

      @click.native   

### 其它

1. 在属性中插入vue变量

            :style="'color:'+ color"
  
2. vm.$parent 父实例 **只读**  

相当于引入子实例的上级实例的this对象

            this.$parent.$refs
            this.$parent.$data
