#### cookie不可跨域

1. cookie在一级域名不同情况下不可跨域访问 但是存在taobao.com和tmall.com可以共享登录状态的场景
2. cookie在二级域名不想同的情况下也不可跨域访问，但是在tieba.baidu.com和zhidao.baidu.com可以共享登录状态的场景

#### taobao.com和tmall.com如何共享登录状态

tmall.com(no cookie)

---> redirect 302: login.taobao.com/jump/ (login)

---> get location:pass.tmall.com/add?+cookie+token

---> jsonp(taobao.com/go/tmall/login-api.php

---> get cookie+token)

---> tmall.com/add?+cookie+token

---> set cookie

---> refresh tmall.com

#### tieba.baidu.com和zhidao.baidu.com可以共享登录状态

所有域下document.cookie = ";path=/;domain=qq.com"

#### 拓展

1. localstorage跨子域解决方案 ： 所有跨域传递信息页面设置document.domain=主域名 + iframe + postMessage()
2. token
3. CSRF
4. SSO单点登陆

