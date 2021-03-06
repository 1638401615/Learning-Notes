# 7.1 HTTP 的缺点

* 通信使用明文（不加密），内容可能会被窃听
* 不验证通信方的身份，因此有可能遭遇伪装
* 无法证明报文的完整性，所以有可能已遭篡改

## 7.1.1 通信使用明文可能会被窃听

* TCP/IP 是可能被窃听的网络

  即使是已经被加密过的通信也会被窥视到通信内容，还是能看到，只是因为加密可能看不懂。

* 加密处理防止被窃听
  1. 通信的加密：通过和 SSL（Secure Socket Layer，安全套接层）或 TLS（Transport Layer Security，安全层传输协议）的组合使用， 加密 HTTP 的通信内容。
  2. 内容的加密：把 HTTP 报文里所含的内容进行加密处理。

## 7.1.2 不验证通信方的身份就可能遭遇伪装

* 任何人都可发起请求：
  1. 无法确定请求发送至目标的 Web 服务器是否是按真实意 图返回响应的那台服务器。有可能是已伪装的 Web 服务器。
  2. 无法确定响应返回到的客户端是否是按真实意图接收响 应的那个客户端。有可能是已伪装的客户端。
  3. 无法确定正在通信的对方是否具备访问权限。因为某些 Web 服务器上保存着重要的信息，只想发给特定用户通信的权限。
  4. 无法判定请求是来自何方、出自谁手。
  5. **即使是无意义的请求也会照单全收。无法阻止海量请求下的 DoS 攻击（Denial of Service，拒绝服务攻击）。**

* 查明对手的证书：

  <img src="D:\学习文件\学习笔记\图解http\笔记图片\SSL证书确定通信方.jpg" style="zoom:80%;" />

## 7.1.3 无法证明报文完整性，可能已遭篡改

* 接收到的内容可能有误

  <img src="D:\学习文件\学习笔记\图解http\笔记图片\中间人攻击.jpg" style="zoom:80%;" />

* 如何防止篡改：

  其中常用的是 **MD5 和 SHA-1 **生成的散列值校验的方法， 以及用来确认文件的**的以 PGP（Pretty Good Privacy，完美隐私）创建的数字签名**方法。

  不论使用哪一种方法，**都需要操纵客户端的用户本人亲自检查验证**下载的文件是否就是原来服务器上的文件。 浏览器无法自动帮用户检查。

# 7.2 HTTP+ 加密 + 认证 + 完整性保护 =HTTPS

## 7.2.1 HTTP 加上加密处理和认证以及完整性保护后即是 HTTPS

## 7.2.2 HTTPS 是身披 SSL 外壳的 HTTP

<img src="D:\学习文件\学习笔记\图解http\笔记图片\HTTP和HTTPS.jpg" style="zoom:80%;" />

* SSL是独立于HTTP的协议，可以用于其他协议中

## 7.2.3 相互交换密钥的公开密钥加密技术

* **共享密钥加密**的困境

  <img src="D:\学习文件\学习笔记\图解http\笔记图片\共享密钥加密.jpg" style="zoom:80%;" />

* 使用两把密钥的**公开密钥**加密

  发送密文的一方使用对方的公开密钥进行加密处理，对方收到被加密的信息后，再使用自己的私有密钥进行解密。（即加密方法公开，解密方法私有）

  ![](D:\学习文件\学习笔记\图解http\笔记图片\公开密钥加密.jpg)

* HTTPS 采用混合加密机制

  **在交换密钥环节使用公开密钥加密方式，之后的建立通信交换报文阶段则使用共享密钥加密方式。**

<img src="D:\学习文件\学习笔记\图解http\笔记图片\混合密钥加密.jpg" style="zoom:80%;" />

## 7.2.4 证明公开密钥正确性的证书

使用由数字证书认证机构（CA，Certificate Authority）和其相关机关颁发的公开密钥证书。

认证机关的公开密钥必须安全地转交给客户端：多数浏览器开发商发布 版本时，会**事先在内部植入**常用认证机关的公开密钥。

<img src="D:\学习文件\学习笔记\图解http\笔记图片\数字证书认证.jpg" style="zoom:80%;" />

* 可证明组织真实性的 EV SSL 证书
* 用以确认客户端的客户端证书

## 7.2.5 HTTPS 的安全通信机制

从仅使用服务器端的公开密钥 证书（服务器证书）建立 HTTPS 通信的整个过程：

<img src="D:\学习文件\学习笔记\图解http\笔记图片\仅用服务端证书建立HTTP通信.jpg" style="zoom:80%;" />

* SSL 和 TLS

  TSL是以 SSL为原型开发的协议，有时会统一称该协议 为 SSL。当前主流的版本是 SSL3.0 和 TLS1.0。

* SSL 速度慢：

  1. 通信慢。

  2. 由于大量消耗 CPU 及内存等资源，导致处理速度变慢。

     <img src="D:\学习文件\学习笔记\图解http\笔记图片\SSL速度慢.jpg" style="zoom:80%;" />

>为什么不一直使用 HTTPS?
>
>1. 每次都加密会消耗太多资源，导致计算机处理请求数量减少；
>2. 节约购买证书的开销
>3. 所以只有在包含个人信息等敏感数据时，才利用 HTTPS 加密通信。
