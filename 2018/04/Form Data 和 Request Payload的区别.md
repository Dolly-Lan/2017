chrome发起http请求的2中不同的信息参数

[相关资料](http://bubuko.com/infodetail-2360733.html)

POST请求1
  
      General:
        Request URL: https://10.95.34.11/skyeye/scene/manager/whitelist
        Request Method: POST    // post请求
        Status Code: 200 OK
        Remote Address: 10.95.34.11:443
        Referrer Policy: no-referrer-when-downgrade
      Response Headers:
        Connection: keep-alive
        Content-Length: 127
        Content-Type: application/json
        Date: Mon, 02 Apr 2018 08:19:33 GMT
      Server: nginx
        Request Headers:
        Accept: application/json, text/plain, */*
        Accept-Encoding: gzip, deflate, br
        Accept-Language: zh-CN,zh;q=0.9
        Cache-Control: no-cache
        Connection: keep-alive
        Content-Length: 156
        Content-Type: application/json;charset=UTF-8   // Content-Type为json类型
        Cookie: session=54d795c5ce94d3372d66beeff51d67b00d50d39847e4d562cf0c7e23b081c2d00c4fcc81a536fb82
        Host: 10.95.34.11
        Origin: https://10.95.34.11
        Pragma: no-cache
        Referer: https://10.95.34.11/skyeye/home/scenes?isFirstComing=true
        User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36
      Request Payload:   // HTTP请求参数为Request Payload类型
        {ip1_type: "ip", ip1: "1.1.1.1", ip2_type: "ip", ip2: "1.1.1.2", scene_type: "asset",…}

POST请求2

    General:
      Request URL: https://10.95.34.11/skyeye/workorder/detail
      Request Method: POST   // POST请求
      Status Code: 200 OK
      Remote Address: 10.95.34.11:443
      Referrer Policy: no-referrer-when-downgrade
    Response Headers:
      Connection: keep-alive
      Content-Length: 167
      Content-Type: application/json
      Date: Mon, 02 Apr 2018 09:10:15 GMT
      Server: nginx
    Request Headers:
      Accept: application/json, text/plain, */*
      Accept-Encoding: gzip, deflate, br
      Accept-Language: zh-CN,zh;q=0.9
      Cache-Control: no-cache
      Connection: keep-alive
      Content-Length: 153
      Content-Type: application/x-www-form-urlencoded    //  Content-Type为x-www-form-urlencoded表单类型
      Cookie: session=54d795c5ce94d3372d66beeff51d67b00d50d39847e4d562cf0c7e23b081c2d00c4fcc81a536fb82
      Host: 10.95.34.11
      Origin: https://10.95.34.11
      Pragma: no-cache
      Referer: https://10.95.34.11/skyeye/home/alarm/detail
      User-Agent: Mozilla/5.0 (Windows NT 6.1; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36
    Form Data:    // HTTP请求参数是form Data 类型
      name: sdfsd
      
同样式post请求，但是提交的参数类型不一样，Form Data和 Request Payload这2项的不同是由于对Request Headers的Content-Type配置不一样，一个是表单类型，
一个是json字符串类型。所以采用那种提交方式需要后端做相应的支持，避免后端获取不到参数
