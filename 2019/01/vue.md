### $event

[官方资料](https://cn.vuejs.org/v2/guide/events.html#内联处理器中的方法)

有时也需要在内联语句处理器中访问原始的 DOM 事件。可以用特殊变量 $event 把它传入方法：

    <button type="submit" @click="submit('msg', $event)"></button>
