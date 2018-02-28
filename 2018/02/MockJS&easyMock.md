## MockJS

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
  占位符只是在属性值字符串中占个位置，并不出现在最终的属性值中，所以需要用引号括起来。

      @string(length) / @string(pool?,min?,max?)   //  英文字符串
      @ctitle( min?, max? )  // 返回中文标题
      @integer(min?, max?)  //返回整数
      @boolean( min?, max?, current?)  // 返回true 或者false

  #### 生成规则插入变量
  
  对list的数据模版必须使用类型符[ ]括起来，再在内部使用es模版语言插入，如果不用[]括起来就没用
  
  
    Mock.mock({
        data: {
          total: 100,
          [`list|${pageSize}`]: [{   
            id: '@integer(0, 100)',
            title: '@ctitle(3, 5)',
            type: '@ctitle(3, 5)',
            days: '@integer(0, 100)',
            day_logs_doing: '@integer(0, 1000)',
            day_logs: 1000,
            month_logs_doing: '@integer(1000, 10000)',
            month_logs: 10000,
            status: '@integer(0, 1)'
          }]
        }
      })
      
  对于添加规则|的数据模版要使用引号，否则无法解析
  
    
    list | 15 : [{
      name: '@string'
    }]
    
    
## easy Mock

### 响应式数据

  为某个属性指定一个 Function。在 Function 中，我们提供了 _req 对象，这使得我们可以通过请求对象编写逻辑，实现响应式数据，如图所示。

    Mock.mock({
      data: {
        _req: function ({_req}) {
          return req
        }
      }
    })
    
    
  解析为：
    
      {
        "data": {
          "_req": {
            "method": "GET",
            "url": "/mock/5a8f7c5f752aaa0d37b35cfd/scene/scene/state",
            "header": {
              "host": "mock",
              "connection": "close",
              "accept": "application/json, */*",
              "user-agent": "Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/59.0.3071.109 Safari/537.36",
              "content-type": "application/json",
              "referer": "http://mock.bfe.360es.cn/mock/5a8f7c5f752aaa0d37b35cfd/scene/scene/state",
              "accept-encoding": "gzip, deflate",
              "accept-language": "zh-CN,zh;q=0.8",
              "cookie": "easy-mock_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJqdGkiOiI1YThmN2I5YjQ1YTQ4YzdmNjdiNjg2ZDEiLCJleHAiOjE1MjA1NjIzMzEsImlkIjoiNWE4ZjdiOWJlZWZkZGE3ZjZjYzUzMDAxIiwiaWF0IjoxNTE5MzUyNzMxfQ.Yjq6tgKIqoOJzuk3mMT1dd5vZYQbphSnJYX0q5Z4hiQ"
            }
          }
        }
      }
    
    通过_req对象可以拿到的参数说明[文档](http://mock.bfe.360es.cn/docs#xiang-ying-shi-shu-ju)
    
