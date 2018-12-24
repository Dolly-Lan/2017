### Response Headers set-cookie

[官方资料](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Set-Cookie)

用来由服务器端向客户端发送 cookie（自动在response返回响应成功后，给浏览器设定cookie）

### 设置cookie httpOnly=true

则不能使用 document.cookie 来读取/操作，御防范跨站脚本攻击（XSS），只能只能从服务端读取和操作。

