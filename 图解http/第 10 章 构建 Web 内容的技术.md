# 10.1 HTML

## 10.1.1 Web 页面几乎全由 HTML 构建

## 10.1.3 设计应用 CSS(让HTML页面更好看)

CSS（Cascading Style Sheets，层叠样式表）可以指定如何展现 HTML 内的各种元素，属于样式表标准之一。CSS 的理念就是让文档的结构和设计分离，达到解耦的目的。

# 10.2 动态 HTML

## 10.2.1 让 Web 页面动起来的动态 HTML

动态 HTML（Dynamic HTML），是指使用**客户端脚本语言（如JavaScript）**将静态的 HTML内容变成动态的技术的总称。

## 10.2.2 更易控制 HTML 的 DOM

DOM 是用以操作 HTML文档和 XML文档的 API（Application Programming Interface，应用编程接口）。使用 DOM 可以将 HTML内 的元素当作对象操作，如取出元素内的字符串、改变那个 CSS 的属性等，使页面的设计发生改变。

使用 DOM 可以将 HTML内 的元素当作对象操作，如取出元素内的字符串、改变那个 CSS 的属 性等，使页面的设计发生改变。

# 10.3 Web 应用

## 10.3.1 通过 Web 提供功能的 Web 应用

<img src=".\笔记图片\动态内容和静态内容.jpg" style="zoom:80%;" />

## 10.3.2 与 Web 服务器及程序协作的 CGI

CGI（Common Gateway Interface，通用网关接口）是指 **Web 服务器在接收到客户端发送过来的请求后转发给程序**的一组机制。

<img src=".\笔记图片\CGI.jpg" style="zoom:80%;" />

## 10.3.3 因 Java 而普及的 Servlet

Servlet 是一种能在服务器上**创建动态内容**的程序。运行在与 Web 服务器相同的进程中，因此受到的负载较小 。Servlet 的运行环境叫做 Web 容器或 Servlet 容器。

<img src="D:\学习文件\学习笔记\图解http\笔记图片\Servlet.jpg" style="zoom:80%;" />

# 10.4 数据发布的格式及语言

## 10.4.1 可扩展标记语言

* XML和 HTML都是从标准通用标记语言 SGML（Standard Generalized Markup Language）简化而成。

* 从 XML文档中读取数据比起 HTML更为简单。由于 XML的结构基 本上都是用标签分割而成的树形结构，因此通过语法分析器 （Parser）的解析功能解析 XML结构并取出数据元素，可更容易地对 数据进行读取。

## 10.4.2 发布更新信息的 RSS/Atom

* RSS（简易信息聚合，也叫聚合内容）和 Atom 都是**发布新闻或博客日志等更新信息文档的格式**的总称。两者都用到了 XML。

## 10.4.3 JavaScript 衍生的轻量级易用 JSON

