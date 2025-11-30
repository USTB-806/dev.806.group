---
title: "HTTP/HTTPS"
date: 2025-11-04
draft: false
---

# HTTP/HTTPS
## HTTP
- HTTP（HyperText Transfer Protocol）超文本传输协议
    - 定义
        - HTTP 是一个在计算机世界里专门在「两点」之间「传输」文字、图片、音频、视频等「超文本」数据的「约定和规范」
            - 应用层协议，双向协议
            - 超文本（HTML、CSS），超链接（一个超文本跳转另一个超文本）
        - 允许客户端与服务器之间进行通信，以请求和传输网页、图片、视频等资源
        - 基于请求-响应模型，客户端发送请求到服务器，服务器处理请求后返回响应
            - 建立连接——客户端（浏览器）与服务器特定端口（默认使用80端口）建立TCP连接（TCP：传输控制协议）
            - 发送请求——客户端发送HTTP请求
                - 请求行
                - 请求头
                - 请求体
            - 处理请求——客户端收到请求，解析内容
            - 返回响应
                - 状态行
                - 响应头
                - 响应体
            - 关闭连接    
 
    - URL（Uniform Resource Locator）统一资源定位符
        - 所谓网址 
        - url=协议名+登录信息+服务器网址+端口号+带层次的文件路径+查询字符串+片段标识符
            - eg：https://user:pass@www.example.com:10/dir/index.htm?uid=1#ch1 
               
    - 请求方法（method）
        - 方法|说明|支持的HTTP协议版本
            -|-|-
            GET|获取资源|1.0、1.1
            POST|传输实体主体|1.0、1.1
            PUT|传输文件|1.0、1.1
            HEAD|获取报文首部|1.0、1.1
            DELETE|删除服务器指定资源|1.0、1.1
            OPTIONS|返回服务器所⽀持的请求⽅法|1.0
            TRACE|回显服务器端收到的请求|1.0
            CONNECT|要求用隧道协议连接代理|1.0
            LINK|建立和资源之间的联系|1.0
            UNLINK|断开连接关系|1.0

    - GET/POST
        - GET
            - 语义：从服务器获取指定的资源
            - 资源可以是静态的文本、页面、图片视频等,参数位置一般是写在URL中，URL规定只能支持 ASCII
        - POST 
            - 语义：根据请求负荷（报文body）对指定的资源做出处理
            - 携带数据的位置一般是写在报文body中，body中的数据可以是任意格式的数据
            - 典型应用场景：登录和上传
       
    - 常见字段 
        - Host：表示服务器主机的地址和端口
        - User-Agent：表示浏览器/操作系统的属性
        - Referer：表示这个页面是从哪个页面跳转过来的
        - Accept：声明可接受的数据格式
        - Cookie：客户端将之前服务器发送的Cookie信息发送回服务器，用于维护用户会话状态
            - 客户端发送请求
            - 服务器创建Session，把SessionId通过Set-Cookie返回客户端
            - 客户端发送其他请求，携带Cookie
            - 服务器通过SessionId查找Session继续后续操作，未找到就重建并返回客户端 
        - Content-Length：表示body中的数据长度
        - Content-Type：表示请求的body中的数据格式
        - Content-Encoding：说明数据的压缩方法
        - Connection：用于客户端要求服务器使用TCP持久连接，以便其他请求复用 
        - Set-Cookie：指示客户端创建、修改或删除一个Cookie
        - Location：重定向
        - Server：描述服务器信息      

    - 五类状态码
        - 状态码|状态码解释|介绍
            -|-|-
            200|OK|表示访问成功
            404|Not Found|没有找到资源
            403|Forbidden|访问被拒绝，比如一些需要权限的页面
            405|Method Not Allowed|不支持所有方法
            500|Internal Server Error|服务器出现内部错误
            504|Gateway Timeout|请求超时
            302|Move temporarily|临时重定向
            301|Moved Permanently|永久重定向
        - -|类别|原因
            -|-|-
            1XX|信息性状态码|接收的请求正在处理
            2XX|成功状态码|请求正常处理完毕
            3XX|重定向状态码|需要进行附加操作以完成请求
            4XX|客户端错误状态码|服务器无法处理请求
            5XX|服务器错误状态码|服务器处理请求出错
    
    - HTTP协议格式 
        - 请求
            - 首行=方法+url+协议版本 
                - eg：GET http://www.example.com/HTTP/1.1 
            - header：描述请求的一些附加信息
                - 冒号分割的键值对，空行表示header部分结束
                - eg：Host: www.example.com
            - Body：描述请求的数据
                - 可以是任何格式的数据，例如表单数据、JSON数据、XML数据等
                - 空行后面的部分，Body允许为空字符串，如果Body存在,则在header中会有⼀个 Content-Length属性来标识Body的长度
        - 响应
            - 首行=版本号+状态码+状态码解释
                - eg：HTTP/1.1 200 OK 
            - header：服务器信息和对响应的描述
                - 冒号分割的键值对，空行表示header部分结束
                - eg：Server: nginx/1.16.0
            - Body：描述请求的数据
                - 如html文档，图片等 
                - 空行后面的部分，如果服务器返回一个html页面，那么html页面内容就是在Body中

## HTTPS
- HTTPS（HyperText Transfer Protocol Secure）超文本传输安全协议
    - 定义 
        - HTTP的安全版本
        - HTTPS=HTTP+SSL/TLS 
            - 在HTTP与TCP层（传输层）之间加入了安全协议（SSL安全套接字层协议、TLS安全传输层协议）
        - 默认使用443端口
    - 工作流程
        - 客户端发起连接请求，声明支持的加密算法
        - 服务器证书发送，发送SSL/TLS证书（CA签名）
        - 客户端验证证书
        - 密钥协商
        - 通信加密
        - 安全数据传输
        - 完整性检查  
