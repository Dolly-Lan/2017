### 自动刷新页面
 
    location.reload()
    
### window.open(url)下载和window.location.href=url下载区别

用window.open()打开新页面 
但是用window.location.href＝"" 却是在原窗口打开的. 
有时浏览器会一些安全设置window.open肯定被屏蔽。例如避免弹出广告窗口。

### 浏览器type=file无法获取上传文件路径

 出于信息安全机制考虑，只能获得文件名
