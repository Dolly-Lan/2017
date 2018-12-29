### expires 属性 和 max-age 属性

[区别：网络资料](https://blog.csdn.net/yingzizizizizizzz/article/details/81347719)

* expires指定失效日期（GMT日期），是一个绝对时间，如果没有指定，则默认为“session（会话）”，即关闭浏览器，则cookie失效
* max-age指定cookie在设置后多少**秒**后失效（单位为：秒），是一个相对值，如果没有指定，则根据expires来计算

### 存

通过document.cookie来设置，每个新的cookie通过指定新的key=value来赋值给document.cookie

代码示例：

    document.cookie = 'key=value'
    
