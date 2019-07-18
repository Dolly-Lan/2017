### Array.sort()

会直接修改数据源

### 正则表达式

    <a[^>]+> //1. 匹配<a 匹配不是>的内容，直到出现>为止
    a.*?b  // 2. 最小匹配 ？ 
    /abc/ig // 3. 忽略大小写，全局匹配字符串abc
    空 // 4. 完整匹配‘1+1’
    空 // 5. 大小写字母或数字32位
    空 // 6. 非0的十进制数字（至少有以为数字，但是不能以0开头）
    var str = 'John Smith'; var reg = /(\w+)\s(\w+)/; str.replace(reg,"$2 $1"); //  7. John Smith => Smith John
    空 // 8. getElementById => get-element-by-id
    空  // 9. 匹配a标签内的href值
    /\d+(\.\d+)?\%/  // 10. 后面跟着百分号的数字
    // 11-1 Regexp实例对象方法
    Regexp.test(str) //匹配字符串中指定的值
    Regexp.compile(str) // 编译正则表达式
    Regexp.exec(str) 	// 找到了匹配的文本，则返回一个结果数组。否则，返回 null
    // 11-2 支持正则表达式的 String 对象的方法
    String.search(reg) 	// 检索与正则表达式相匹配值的位置
    String.match(reg)	// 找到一个或多个正则表达式的匹配值
    String.replace(reg) // 替换与正则表达式匹配的子串
    String.split(reg) 	// 把字符串按照正则表达式匹配规则分割为字符串数组
    
    
### window.open()

[MDN](https://developer.mozilla.org/zh-CN/docs/Web/API/Window/open)

参数： open(url, windowName, options)
返回值： open成功后新窗口的window对象，如果调用失败，返回值会是 null 。**如果父子窗口满足“同源策略”，你可以通过这个引用访问新窗口的属性或方法**。

### onload

[MDN](https://developer.mozilla.org/en-US/docs/Web/API/Window/load_event)

当一个资源及其依赖资源（支持该事件的标签：body, frame, frameset, iframe, img, link, script）已完成加载时，将触发load事件，如果在window上绑定，则监听包括当前window下所有资源加载完成。
