### typeof 和 instanceof 用法

    typeof + 变量
    变量 + instanceof + Array/Funtion/ObjectString/....


### Array.find(fun) 函数

  找到数组中符合fun条件的第一个元素值
        
      let obj = {}
      let arr = [{
        value: 1,
        label: '猫'
      }, {
        value: 2,
        label: '狗'
      }]
      obj = arr.find(item => {    // obj 为　{value: 1, label: '猫'}
        return item.value === 1
      })
       
### 删除数组最后一位（影响原数组）

    Array.pop()
    
### new Date().getTime()方法

    获取到毫秒单位的时间戳
    
    
### form表单 submit click提交

[Press Enter to Submit 背后的那些事](http://david-chen-blog.logdown.com/posts/177766-how-forms-submit-when-pressing-enter)

当button的type指定为submit的时候，会自动触发click事件，然后再触发submit事件

    <form>
        <input type="text">
        <button type="submit" onclick="submit">button</button>
    </form>
    
### userAgent

    ie11: u.indexOf('Trident') > -1 && u.indexOf("rv:11.0") > -1, // IE11 （IE11内核使用了mozilla的gecko内核，同火狐一致）
    isIe: u.indexOf('compatible') > -1  && u.indexOf("MSIE") > -1, // IE（< IE11）内核
    isEdge: u.indexOf("Edge") > -1 && u.indexOf('compatible') > -1  && u.indexOf("MSIE") > -1,
    presto: u.indexOf('Presto') > -1, // opera内核
    webKit: u.indexOf('AppleWebKit') > -1, // 苹果、谷歌内核
    Firefox: u.indexOf('Firefox') > -1 && u.indexOf('KHTML') === -1, // 火狐内核
    mobile: !!u.match(/AppleWebKit.*Mobile.*/), // 是否为移动终端
    ios: !!u.match(/\(i[^;]+;( U;)? CPU.+Mac OS X/), // ios终端
    android: u.indexOf('Android') > -1 || u.indexOf('Linux') > -1, // android终端或者uc浏览器
    iPhone: u.indexOf('iPhone') > -1, // 是否为iPhone或者QQHD浏览器
    iPad: u.indexOf('iPad') > -1, // 是否iPad
    webApp: u.indexOf('Safari') === -1, // 是否web应该程序，没有头部与底部
    weixin: u.indexOf('MicroMessenger') > -1, // 是否微信 （2015-01-22新增）
    qq: u.match(/\sQQ/i) === ' qq' // 是否QQ
        
    


