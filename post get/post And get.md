# Post get 的区别
  
## GET和POST是HTTP请求的两种基本方法

  
## 最直观的区别就是 

    GET在浏览器回退时是无害的，而POST会再次提交请求。

 
    GET产生的URL地址可以被Bookmark，而POST不可以。

    
    GET请求会被浏览器主动cache，而POST不会，除非手动设置。

    
    GET请求只能进行url编码，而POST支持多种编码方式。

    
    GET请求参数会被完整保留在浏览器历史记录里，而POST中的参数不会被保留。

    
    GET请求在URL中传送的参数是有长度限制的，而POST么有。

    
    对参数的数据类型，GET只接受ASCII字符，而POST没有限制。

    GET比POST更不安全，因为参数直接暴露在URL上，所以不能用来传递敏感信息。

    GET参数通过URL传递，POST放在Request body中。

## request
    代表HTTP请求的对象.在浏览器向服务器发送请求之后, 
    服务器接受到请求, 在调用service方法处理请求之前， 
    会创建Request对象， 并把所有的请求信息( 请求行、
    请求头、请求实体 ) 全部封装到Request对象中

## HTTP

 HTTP是基于 TCP/IP的 关于数据如何在万维网中通信的协议HTTP的底层是TCP/IP 所有GET和POST的底层也是TCP/IP  也就是说 GET和POST都是TCP的链接


## GET和POST的的重点区别 

####GET产生一个TCP数据包；POST产生两个TCP数据包。

    对于GET方式的请求，浏览器会把http header和data一并发送出去，服务器响应200（返回数据）；

    而对于POST，浏览器先发送header，服务器响应100 continue，浏览器再发送data，服务器响应200 ok（返回数据）。

    因为POST需要两步，时间上消耗的要多一点，看起来GET比POST更有效。


####因此Yahoo（雅虎）团队有推荐用GET替换POST来优化网站性能。但这是一个坑！跳入需谨慎。为什么？

    1. GET与POST都有自己的语义，不能随便混用。

    2. 据研究，在网络环境好的情况下，发一次包的时间和发两次包的时间差别基本可以无视。
    而在网络环境差的情况下，两次包的TCP在验证数据包完整性上，有非常大的优点。

    3. 并不是所有浏览器都会在POST中发送两次包，Firefox就只发送一次















