### BFC盒模型布局模式

当触发改模式时，则会出现以下情形：

  * 相邻盒子外边距不再折叠
  * 清除浮动
  * 防止文字环绕

只有通过以下css设置才会触发：

  * float的值不为none
  * position的值不为static或者relative
  * display的值为 table-cell, table-caption, inline-block, flex, 或者 inline-flex中的其中一个
  * overflow的值不为visible

