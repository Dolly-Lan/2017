# 20170901

### html

#### readonly和disable区别

同：用户不能够更改表单域中的内容

不同：

1. readonly只对input(text / password)和textarea有效， disabled对所有表单元素有效

2. readonly不可编辑，可复制，可选择,可以接收焦点但不能被修改，后台会接收到传值
disabled不可编辑，不可复制，不可选择，不能接收焦点,后台也不会接收到传值。

