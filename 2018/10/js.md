### 自动刷新页面
 
    location.reload()
    
### window.open(url)下载和window.location.href=url下载区别

 * window.open(): 
  
   * 用window.open()打开新页面 
   * 有时浏览器会一些安全设置window.open肯定被屏蔽。例如避免弹出广告窗口。
   
 * location.href: 
 
   * 是在原窗口打开的
   * 两个及以上的window.location.href，只执行最后一个
   
### 单个下载、批量下载静态资源

 * 单个下载
 
  * window.open()会被拦截，且打开的是新窗口
  * window.href不会被拦截，且在本窗口打开
  
 * 批量下载
 
  * window.open()会被拦截，且会切换tab
  * window.href 当连续调用两个及以上的window.location.href，只执行最后一个
  * 模拟a标签下载
  
        download(url) {
          let link = document.createElement('a')
          link.setAttribute('download', name)
          link.setAttribute('href', url)
          Object.assign(link.style, {
            opacity: 0,
            position: 'absolute',
            top: 0
          })
          document.body.appendChild(link)
          link.click()
          setTimeout(() => document.body.removeChild(link), 2000)
        }


### 浏览器type=file无法获取上传文件路径

 出于信息安全机制考虑，只能获得文件名
