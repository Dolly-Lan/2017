### 修饰符

#### .stop

阻止事件冒泡

    <div @click="test">
      <a @click.stop="doThis"></a>
    </div>

#### .trim

自动过滤用户输入的首尾空白字符

    <input v-model.trim="msg">
