### 表单enter事件触发提交

包含input单行输入（type="text"）数量为1时，无论含有多少其他类型的表单组件，则Enter会自动提交表单，为浏览器默认事件。

如下示例，当鼠标focus input输入框，按Enter事件，则自动提交到action指定的url中

  <form action="url">
    <input type="text" />
  </form>
  
解决办法：增加一个隐藏的input单行文本输入框：

  <form action="url">
    <input type="text" />
    <input type="text" style="display:none;" />
  </form>
