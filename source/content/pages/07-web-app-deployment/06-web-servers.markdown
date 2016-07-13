title: Web 服务器
category: page
slug: web-servers
sortorder: 0706
toc: False
sidebartitle: Web 服务器
meta: Web 服务器相应对静态内容的 HTTP 请求，同时作为 Python web 应用的反向代理。
translators: blog.chriscabin.com
updated: 2016-07-13 19:00

# Web 服务器
Web 服务器响应来自客户端的
[超文本传输协议](http://en.wikipedia.org/wiki/Hypertext_Transfer_Protocol) （HTTP）请求，然后给客户端发送回应，包括一个状态码，通常还有诸如 HTML、XML、或 JSON 格式的响应内容。 


## 为何 Web 服务器是必要的？
Web 服务器和 web 客户端如同阴和阳。服务器和客户端使用万维网（World Wide Web, WWW）的标准语言沟通。 正式因为有了标准语言，老旧的 Mozilla Netscape 浏览器才依旧能够和一个现代的 web 服务器沟通，例如 Aache 或者 Nginx，即使它不能像现代浏览器那样较好地渲染页面样式。

采用从客户端到服务器，再从服务器回到客户端的请求和响应模型的 Web 基础语言仍然和 1989 年由 [Tim Berners-Lee](http://www.w3.org/People/Berners-Lee/)在 CERN 发明的 Web 基础语言保持一致。现代浏览器和 web 服务器只是简单地扩展了该语言，从而使它符合现代标准。

## Web 服务器实现
Web 服务器的思想概念可以通过不同的方式来实现。以下列出的几种 web 服务器实现都有着不同的特性、扩展和配置。

*  [Apache HTTP 服务器](/apache-http-server.html) 在 20 多年里一直是因特网中最常部署的 web 服务器。

* [Nginx](/nginx.html) 是前 100 000 个网站中第二常用的 web 服务器，并且它通常作为 [Python WSGI 服务器](/wsgi-servers.html) 的反向代理。

* [Caddy](/caddy.html) 是 web 服务器中的新星，专注服务启用了 HTTPS 的 HTTP/2 协议。


## 客户端请求
给 web 服务器发送请求的客户端通常是浏览器，例如 IE、Firefox、Chrome，但是它也可以是：

* 无头浏览器，通常用于测试，例如
  [phantomjs](http://phantomjs.org/)；
* 命令行实用工具，比如 [wget](https://www.gnu.org/software/wget/)
  和 [cURL](http://curl.haxx.se/)；
* 文本浏览器，如
  [Lynx](http://lynx.browser.org/)；
* web 爬虫。

Web 服务器处理来自上述列出的客户端发出的请求。Web 服务器处理结果是
[响应码](https://developer.mozilla.org/en-US/docs/HTTP/Response_codes)，通常还有响应内容。但有些状态码，例如 204（无内容）和 403（禁止访问），就没有响应内容。

在一个简单的例子中，客户端会请求静态资源，如一幅图片或者 JavaScript 文件。请求的文件存放在 web 服务器文件系统中的一个位置，并且已被授权访问；然后，web 服务器会给客户端发送这个文件，同时发送一个值为 200 的状态码。如果客户端已经请求过这个文件了，并且文件并没有发生变动，那么 web 服务器将会传递回一个值为 304（未修改）的响应来标记客户端已经获取了最新版本的文件了。

<img src="/img/web-browser-server-requests.png" width="100%" class="technical-diagram" alt="Web server and web browser request-response cycle" />

Web 服务器会根据浏览器的请求给它发送文件。在第一次请求中，浏览器会访问 "www.fullstackpython.com" 地址，然后服务器作为响应会发送 HTML 格式的 index.html 文件。这个 HTML 文件包含了其他文件的引用，比如 style.css 和 script.js，然后浏览器会向服务器请求那些文件。

发送静态资源（如 CSS 和 JavaScript 文件）时会占用大量的网络带宽，这就是在可能的情况下使用内容分发网络（CDN）来为 [静态资源提供服务](/static-content.html) 非常重要的原因。


## Web 服务器相关的资源
* [HTTP/1.1 规格说明](http://www.w3.org/Protocols/rfc2616/rfc2616.html)

* 由 W3C 提供的完整的
[HTTP 状态码](http://www.w3.org/Protocols/rfc2616/rfc2616-sec10.html) 列表资料。

* [4 个你应当一直使用的 HTTP 安全标头](http://ibuildings.nl/blog/2013/03/4-http-security-headers-you-should-always-be-using)

* 如果你正想通过构建一个 web 服务器来学习它的话，这里列出的
  [第一部分](http://ruslanspivak.com/lsbaws-part1/),
  [第二部分](http://ruslanspivak.com/lsbaws-part2/) 和 [第三部分](http://ruslanspivak.com/lsbaws-part3/) 就是教你如何使用 Python 编写 web 服务器的优秀教程。

* [rwasa](https://2ton.com.au/rwasa/) 是一款新发布的 web 服务器，它采用汇编语言编写，没有额外的依赖，并被证明比 Nginx 还要快。值得看看这个基准，来看看这款服务器是否符合你的需求；当然，得要在最快的性能和未经测试的 web 服务器之间做权衡。


## Web 服务器学习清单
1. 选择一个 web 服务器。通常推荐 [Nginx](http://nginx.org/en/)，当然 [Apache](http://httpd.apache.org/) 也是一个不错的选择。

1. 创建一个 SSL 证书。对于测试来说，使用一个自签名的证书即可；而对于产品应用，就到 [Digicert](http://www.digicert.com/) 上购买一个证书。配置 web 服务器以启用 SSL。你需要 SSL，从而仅提供 HTTPS 的流量服务，这样便可以阻止用户输入未加密的安全问题发生。

1. 配置 web 服务器，从而提供静态文件，如 CSS、JavaScript 和图片的访问服务。

1. 一旦你设置了 [WSGI 服务器](/wsgi-servers.html)，你就需要配置 web 服务器来传送动态内容。

