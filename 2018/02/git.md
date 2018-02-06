### 过滤提交文件到git上 

[参考资料](http://blog.csdn.net/zhanlurbh/article/details/50888106)

1. .gitignore

    git bash创建.gitignore文件，window下无法创建带“.”文件名文件
  
        touch .gitignore

2. 配置语法：

    以斜杠“/”开头表示目录；

    以星号“*”通配多个字符；

    以问号“?”通配单个字符

    以方括号“[]”包含单个字符的匹配列表；

    以叹号“!”表示不忽略(跟踪)匹配到的文件或目录

3. 代码示例:
    
        /* 忽略提交.idea为名的目录*/
        .idea/ 
        /* 忽略提交这个目录*/
        xenadmin/web/node_modules
        /* 忽略所有以egg为后缀的文件*/
        *.egg
    
