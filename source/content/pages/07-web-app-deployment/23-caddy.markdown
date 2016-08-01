title: Caddy
category: page
slug: caddy
sortorder: 0723
toc: False
sidebartitle: Caddy
meta: Caddy 是一个使用 Go 语言开发的 HTTP 服务器，它强调现代安全标准和加密。
translators: blog.chriscabin.com
updated: 2016-08-01 10:40


# Caddy
[Caddy](https://caddyserver.com/) 是一个相对较新的 HTTP 服务器，它于 2015 年创建并使用 [Go](https://golang.org/) 语言编写。
这个服务器的哲学和设计强调使用 HTTP/2 协议的随处可见的 HTTPS。


## 如何在 Python 部署中使用 Caddy？
Caddy 可以用作本地部署测试，或者作为一个 HTTP 服务器成为生成部署中的一部分，或者可以使用 [代理指令](https://caddyserver.com/docs/proxy) 作为反向代理。

<div class="well see-also">Caddy 是<a href="/web-servers.html">web 服务器</a> 概念的一种实现。在 Learn how these pieces fit together in the <a href="/deployment.html">部署</a>章节学习如何将这些部分组合在一起或者查看所有主题的<a href="/table-of-contents.html">目录</a></div>


### 常见的 Caddy 资源
* [深入 Caddy 内部](https://blog.gopheracademy.com/caddy-a-look-inside/)
展示并解释了一些构建这个服务器的 Go 代码。

* 在 [Caddy 服务器官方文档](https://caddyserver.com/docs) 中可以查看哪些指令能够放在一个 Caddy 配置文件中。

* [Caddy：一个支持 HTTP/2 的现代 web 服务器](http://engineeredweb.com/blog/2015/caddy-web-server/)
是一个简单的概要，说明如何安装 Caddy，并使用简单的样例配置文件进行配置。

* [使用 Caddy 并在本地启用 HTTP 2.0](http://tobias.is/blog/test-http2-localhost-caddy-ssl/)
说明如何使用一个自签名的证书，并使用一个 HTTP/2 web 服务器进行开发。

* [Caddy 免费？](https://caddyserver.com/blog/is-caddy-free) 
说明了 Caddy 用于持续开发服务器所使用的捐助和赞助模式。主旨是服务器可以免费克隆、下载和使用。
目前使用赞助和额外的捐款进行后续的开发工作。

