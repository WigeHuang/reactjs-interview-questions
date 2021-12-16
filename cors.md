要明白什么是跨域之前，首先要明白什么是同源策略？

同源策略就是用来限制从一个源加载的文档或脚本与来自另一个源的资源进行交互。那怎样判断是否是同源呢？

如果协议，端口（如果指定了）和主机对于两个页面是相同的，则两个页面具有相同的源，也就是同源。也就是说，要同时满足以下3个条件，才能叫同源：

协议相同
端口相同
主机相同

介绍
关于跨域问题有很多的解决方案，这里我们总结一下目前最通用最强大的解决方案：CORS。

W3C 的 Web 工作组推荐了一种新的机制，即跨域资源共享（Cross-origin Resource Sharing），简称CORS。其实这个机制就是实现了跨站访问控制，使得安全地进行跨站数据传输成为可能。

跨源资源共享标准( cross-origin sharing standard) 使得以下场景可以使用跨站 HTTP 请求：

使用 XMLHttpRequest 或 Fetch发起跨站 HTTP 请求。
Web 字体 (CSS 中通过 @font-face 使用跨站字体资源)，因此，网站就可以发布 TrueType 字体资源，并只允许已授权网站进行跨站调用。
WebGL 贴图
使用drawImage绘制
Images/video 画面到canvas.
样式表（使用 CSSOM）
Scripts (for unmuted exceptions)
CORS分为简单请求和复杂请求，处理方法也是有不同的，所以我们分别总结。

简单请求
什么是简单请求呢？同时满足以下两个条件，就是简单请求：

请求是下列之一：
HEAD
GET
POST
HTTP的头信息不超出以下几种字段：
Accept
Accept-Language
Content-Language
Last-Event-ID
Content-Type：只限于三个值application/x-www-form-urlencoded、multipart/form-data、text/plain
实现方法非常简单，只需要把服务器的响应报文里的Access-Control-Allow-Origin设置为*或者包含由 Origin指明的站点。

Access-Control-Allow-Origin是HTTP响应报文中的一个字段，Origin是HTTP请求报文中的以一个字段,如果不清楚这两个字段的话，可以自行查阅关于HTTP报文的知识，比如HTTP | MDN。

复杂请求
如果不是简单请求，那就是复杂请求，比如请求的方法是PUT或者DELETE，比如Content-Type字段的类型是application/json，比如设置了自定义头信息。

复杂请求就是比简单请求多了个预检请求（preflight）而已。

预检请求就是浏览器先询问服务器，当前网页所在的域名是否在服务器的许可名单之中，以及可以使用哪些HTTP动词和头信息字段。只有得到肯定答复，浏览器才会发出正式的XMLHttpRequest请求，否则就报错。

预检请求用的请求方法是OPTIONS，表示这个请求是用来询问的。头信息里面，关键字段是Origin，表示请求来自哪个源。除了Origin字段，还有两个字段非常重要：Access-Control-Request-Method和Access-Control-Request-Headers，分别表示允许的请求方法和请求头。

举一个具体的例子：

现在，我们有一个页面向服务器发送了一个POST请求，并且我们自己定义了一个请求头字段My-HEADER，这时候浏览器就会首先发送一个OPTION请求来做预检请求，请求头里有以下字段：

Access-Control-Request-Method: POST
Access-Control-Request-Headers: My-HEADER
如果预检请求成功的话，响应头里的内容如下：

Access-Control-Allow-Origin: http://example.com //表明服务器允许http://example.com的请求
Access-Control-Allow-Methods: POST, GET, OPTIONS //表明服务器可以接受POST, GET和 OPTIONS的请求方法
Access-Control-Allow-Headers: My-HEADER //传递一个可接受的自定义请求头列表
Access-Control-Max-Age: 3000000 //告诉浏览器，本次预检请求的响应结果有效时间是多久
总结
以上就是CORS方法解决跨域问题的流程，CORS支持所有类型的HTTP请求，是目前跨域问题的根本解决方案。