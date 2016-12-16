title: Nginx
category: page
slug: nginx
sortorder: 0721
toc: False
sidebartitle: Nginx
meta: Nginx 是一个部署普遍的 web 服务器，它同时也可以作为 WSGI Python web 应用的反向代理。
translators: blog.chriscabin.com
updated: 2016-08-01 08:00


# Nginx
Nginx 是 [前 10 万个网站中第二常用的 web 服务器](http://w3techs.com/technologies/cross/web_server/ranking)。Nginx 也可以作为 Python [WSGI 服务器](/wsgi-servers.html) 或者甚至是其它 web 服务器（例如 Apache）的反向代理，用于处理请求并回传响应。

<img src="/img/web-servers-map.png" width="100%" alt="Python web application deployments rely on Nginx either as a web server or reverse proxy for WSGI servers." class="technical-diagram" />


<div class="well see-also">Nginx 是<a href="/web-servers.html"> web 服务器</a> 概念的一种实现。在<a href="/deployment.html">部署</a> 章节学习这些部分是如何组合在一起的或者查看所有主题的<a href="/table-of-contents.html">目录</a></div>


## 我该使用 Nginx 还是 Apache HTTP 服务器？
让我们认清这两款“竞争”的服务器：它们都是非常棒的开源项目，并且都能够很好地为你的 web 应用部署提供服务。事实上，许多全球顶级的 web 应用在它们许多部署步骤中都同时使用这两款服务器，通过完整的 HTTP 请求—响应周期。

相对于 Apache，我个人使用 Nginx 更为频繁，因为它的配置文件感觉写起来更容易，并且有更少的可选模板。

这也有点懒惰的成分：Nginx 工作得很好，它从不会给我带来问题。所以，我坚持使用我久经沙场的 Ansible [配置管理](/configuration-management.html) 文件来设置 Nginx 使用 HTTPS 和 SSL/TLS 证书。

## Nginx 安全防护
通过系统包管理器或者源码编译进行标准安装后的默认 Nginx 配置是一个很好的安全基础。
然而，最开始几次尝试设置密码和重定向会让人很疑惑。一个非常好的办法是阅读相关教程来确保你在被 HTTP(S) 配置折磨时避免最常见的安全错误

* [黑客新闻破坏了我们的网站——Nginx 和 PageSpeed 如何修复问题](https://www.airport-parking-shop.co.uk/blog/hacker-news-broke-site-nginx-pagespeed-fixed-problem/)
  主要说明了优化 Nginx 配置以实现更高效地 SSL 连接。这篇文章也包括了使用 Ansible 和 Pagespeed 模块的[配置管理](/configuration-management.html)，其中，Pagespeed 模块是 Google 为 Nginx 和 [Apache HTTP 服务器](/apache-http-server.html) 开发的模块。

* [使用 Let's Encrypt 和 Nginx 增强 Web 部署安全](https://letsecure.me/secure-web-deployment-with-lets-encrypt-and-nginx/ )
  详细演示了在 Ubuntu 14.04 下使用 Nginx 设置 HTTPS。

* [如何在 Ubuntu 14.04 上添加 Nginx 安全防护](https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-on-ubuntu-14-04)
  说明了 SSL 配置和 IP 地址黑名单，然后提供了其它一些更高级的安全模块教程。

* [在 Nginx 上增强 SSL 安全](https://raymii.org/s/tutorials/Strong_SSL_Security_On_nginx.html)
  说明了如何缓和高调的 SSL 攻击，例如
  [Logjam](https://weakdh.org/),
  [Heartbleed](http://heartbleed.com/)
  和 [FREAK](https://freakattack.com/)。


## 常见 Nginx 资源
* 在 [开源应用架构一书](http://www.aosabook.org/en/index.html) 中的 [Nginx 章节](http://www.aosabook.org/en/nginx.html) 详细说明了为何 Nginx 以某种方式扩展构建，并且拥有很棒的部署之旅课程。

* [Nginx 内部：我们如何针对性能和扩展性进行设计](http://nginx.com/blog/inside-nginx-how-we-designed-for-performance-scale/) 
是一篇来自 Nginx 开发者的博客，说明了他们为何相信他们的架构模型要比其它构建 web 服务器的方法更加高效，更具扩展性。

* [测试驱动 web 服务器配置](https://gdstechnology.blog.gov.uk/2015/03/25/test-driving-web-server-configuration/)
是一个非常好的故事，说明了如何反复应用配置变动，例如路由流量到 [Piwik](http://piwik.org/) 进行[web 分析](/web-analytics.html)、作为应用后端进行反向代理、以切当的方式终止 TLS 连接。
阅读一个写得很好的软件部署文章可以让人映像深刻，就像这篇来自政府机关的文章，虽然 UK 政府数字服务，还有美国 18F 以及美国数字服务形成了比最典型的机关更为可靠的文化。

* [针对开发者的 Nginx 介绍](http://carrot.is/coding/nginx_introduction) 给出了最初几步来配置 Nginx 并运行它。

* [一个更快的 Web 服务器：用 Nginx 替代 Apache](http://arstechnica.com/business/2011/11/a-faster-web-server-ripping-out-apache-for-nginx/)
说明了在某些情况下为了提升性能可以使用 Nginx 替换 Apache。

* [Nginx 对比 Apache：我们的看法](https://www.nginx.com/blog/nginx-vs-apache-our-view/)
由 Nginx 背后的开发者以第一方视角说明 web 服务器之间的差别。

* [使用 Nginx 速度限制](http://lincolnloop.com/blog/rate-limiting-nginx/) 说明了如何缓解使用 Nginx 速度限制进行密码暴力猜测尝试的问题。

* [Nginx 使用动态上游](http://tenzer.dk/nginx-with-dynamic-upstreams/)
是一篇非常重要的笔记，说明了如果你正在使用 Nginx 作为反向代理，如何使用变化的主机名设置你的上游 WSGI 服务器。

* [Nginx 缓存](https://serversforhackers.com/nginx-caching/) 说明了如何设置 Nginx 用于缓存 HTTP 请求，这通常可以使用 Varnish 完成，但是也可以使用 `proxy_cache` 和相关指令交给 Nginx 处理。

* [Nginx web 服务器教程](http://articles.slicehost.com/nginx) 是最旧但也最好的教程，它说明了如何设置之前版本的 Nginx。

* [Nginx 中使用动态日志格式](https://benwilber.github.io/nginx/syslog/logging/2015/08/26/dynamic-log-formats-in-nginx.html) 
说明了在 Nginx 中如何使用 HttpSetMiscModule 模块转换变量，并将输入映射到日志的可控制输出中。作者使用这种技术进行像素追踪，这种方法也可以用于其它目的，例如高级调试。

