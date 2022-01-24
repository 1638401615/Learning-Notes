# 9.1 基于 HTTP 的协议

HTTP 功能上的不足可通过创建一套全新的协议来弥补。可是目前基 于 HTTP 的 Web 浏览器的使用环境已遍布全球，因此无法完全抛弃 HTTP。所以只能基于HTTP增加一些新的协议规则和功能。

# 9.2 消除 HTTP 瓶颈的 SPDY

## 9.2.1 HTTP 的瓶颈

* Ajax 的解决方法:一种有效利用 JavaScript 和 DOM（Document Object Model，文档对象模型）的操作，以达到**局部 Web 页面替换加载**（减少响应中传输的数据量）的异步通信手 段。
* Comet 的解决方法：通过延迟应答，模拟实现服务器端向客户端推送（Server Push）的功能。服务器端接收到请求，Comet 会先将响应置于挂起状态，当服务器端有内容更新时，再返回该响应。

<img src=".\笔记图片\Comet通信.jpg" style="zoom:80%;" />

## 9.2.2 SPDY的设计与功能

<img src=".\笔记图片\SPDY的设计.jpg" style="zoom:80%;" />

使用 SPDY 后，HTTP 协议额外获得以下功能:

* 多路复用流
* 赋予请求优先级
* 压缩 HTTP 首部
* 推送功能
* 服务器提示功能

# 9.3 使用浏览器进行全双工通信的 WebSocket

## 9.3.2 WebSocket 协议

协议特点：

* 推送功能：可以由**服务器向客户端**推送数据；
* 减少通信量（只要建立起 WebSocket 连接，就希望一直保持连接状态。且WebSOcket首部信息比较小）

<img src=".\笔记图片\WebSocket通信.jpg" style="zoom:80%;" />

* WebSocket API

  JavaScript 可调用“The WebSocket API”内提供的 WebSocket 程序接口，以实现 WebSocket 协议下全双工通信。

# 9.4 期盼已久的 HTTP/2.0

* HTTP/2.0 的 7 项技术及讨论：

  <img src=".\笔记图片\HTTP2.0技术讨论.jpg" style="zoom:80%;" />

# 9.5 Web 服务器管理文件的 WebDAV

## 9.5.1 扩展 HTTP/1.1 的 WebDAV

* 集合（Collection）：是一种统一管理多个资源的概念。以集合为 单位可进行各种操作。也可实现类似集合的集合这样的叠加。 

* 资源（Resource）：把文件或集合称为资源。 

* 属性（Property）：定义资源的属性。定义以“名称 = 值”的格式执 行。 

* 锁（Lock）：把文件设置成无法编辑状态。多人同时编辑时，可 防止在同一时间进行内容写入。

## 9.5.2 WebDAV 内新增的方法及状态码

