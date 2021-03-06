## 读`图解HTTP`笔记
---

### tcp/ip 协议簇

### 四层结构 与 三次握手
应用层 -> http, dns, ftp -> dns(domain name system)

传输层 -> tcp, udp

网络层 -> ip -> arp(address resolution protocol)

链路层

三次握手 (sync, ack)

### 关键名次

uri (统一 资源 标识符)  url (表示资源地址)

http:// user:pass@ www.example.com: 80   /dir/index.html ?uid=1#ch

协议     登录信息    服务器地址         端口 呆层次的路径       查询字符串

### 请求报文
请求方法、请求uri、协议版本、可选的请求首部、内容实体

### 响应报文
协议版本、状态码、解释状态码的原因短语、可选的请求首部、内容实体

* 不访问特定资源，对服务器本身发起请求

### 请求方法
| method  |                     用途                     |
| :-----: | :------------------------------------------: |
|   GET   |                   获取资源                   |
|  POST   |                 传输实体主体                 |
|   PUT   |            传输文件，不带验证机制            |
|  HEAD   |                 获取报文首部                 |
| DELETE  |                   删除文件                   |
| OPTIONS |               询问支持的method               |
|  TRACE  | 追踪路径，查询发送出去的请求怎样被加工、篡改 |
| CONNECT |            邀请用隧道协议连接代理            |

### 状态码
| code  |                   释义                   |
| :---: | :--------------------------------------: |
|  1xx  |               信息性状态码               |
|  2xx  |         成功状态码 200、204、206         |
|  3xx  | 重定向状态码 301、302、303、**304**、307 |
|  4xx  |      客户端错误 400、401、403、404       |
|  5xx  |      服务端错误 500、502、503、504       |

### HTTPS
http的不足：
```
1、通信使用明文，内容可能被窃取
2、不验证通信方的身份，因此可能遭遇伪装
3、无法证明报文的完整性，所以有可能被篡改
```

https = http + 加密 + 认证 + 完整性保护

**ssl，tsl**

https的不足：
```
1、消耗网络资源
2、消耗cpu和内存等硬件资源
```

### websocket
简历在http基础上协议，连接的发起端仍然是客户端，建立连接后，就不区分客户端或服务端了。
**建立连接后，需要完成一次握手的步骤来切换websocket通信**

### QUIC
[科普：QUIC协议原理分析](https://zhuanlan.zhihu.com/p/32553477)