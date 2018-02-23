### 语法：

[文档](https://github.com/nuysoft/Mock/wiki/Syntax-Specification#%E6%95%B0%E6%8D%AE%E6%A8%A1%E6%9D%BF%E5%AE%9A%E4%B9%89%E8%A7%84%E8%8C%83-dtd)

  #### 数据模板
  
  数据模板中的每个属性由 3 部分构成：属性名、生成规则、属性值：

    // 属性名   name
    // 生成规则 rule
    // 属性值   value
    'name|rule': value
    
  #### 数据占位符
  
  [详细文档](https://segmentfault.com/a/1190000010211622)

  即Mock.Random方法， 在模板数据中被称为占位符，用于生成各种类型的随机数据，让数据更真实。

    @string(length) / @string(pool?,min?,max?)   //  英文字符串
    @ctitle( min?, max? )  // 返回中文标题
    @integer(min?, max?)  //返回整数
