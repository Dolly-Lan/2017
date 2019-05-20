### 全局对象

#### __dirname

表示当前执行脚本所在的目录

### path

#### resolve([...paths])

[中文文档](http://nodejs.cn/api/path.html#path_path_resolve_paths)

无参数：

  const path = require('path')
  path.resolve()  // 等同于__dirname
  
有参数：

[参考资料](https://www.cnblogs.com/zytt/p/9038598.html)

### window下的node升级

由于window下无stable命令，则需要从官网上下载安装包进行重新安装
