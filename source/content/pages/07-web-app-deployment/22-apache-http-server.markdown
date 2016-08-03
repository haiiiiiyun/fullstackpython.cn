title: Apache HTTP 服务器
category: page
slug: apache-http-server
sortorder: 0722
toc: False
sidebartitle: Apache HTTP 服务器
meta: Apache HTTP 服务器是一个广泛部署的 web 服务器，它通常和 WSGI 一起为 Python web 应用提供服务。
translators: blog.chriscabin.com
updated: 2016-08-01 10:00


# Apache HTTP 服务器
[Apache HTTP 服务器](https://httpd.apache.org/) 是一个广泛部署的 web 服务器，它能够组合使用一个 WSGI 模块，如 mod\_wsgi 或者一个单独的 [WSGI 服务器](/wsgi-servers.html)，来运行 Python web 应用。


## Apache HTTP 服务器为何很重要？
Apache 仍然是最长部署的 web 服务器，并且占据统治地位 20 余年。由于它使用广泛，所以有大量的教程和开发者开发的开源模块可供任何人使用。

Apache 开发起源于 1994 年中期，当时它是 [NCSA HTTP Server](https://en.wikipedia.org/wiki/NCSA_HTTPd) 项目的一个分支。
到了 1996 年早期，Apache 占据了统治地位，但是由于开发关注大大减少导致 NCSA 进度停滞，进而导致 NCSA 服务器开发停滞。

<div class="well see-also">Apache HTTP 服务器<a href="/web-servers.html">web 服务器</a> 概念的一种实现。在<a href="/deployment.html">部署</a> 章节学习如何将这些组合在一起，或者查看所有主题的<a href="/table-of-contents.html">目录</a></div>



### Apache HTTP 服务器相关资源
* [官方项目文档主页](http://httpd.apache.org/docs/current/) 包含一节说明如何处理认证、安全和动态内容的教程。

* [反向代理](http://www.apachetutor.org/admin/reverseproxies) 说明了如何使用 `mod_proxy` 设置 Apache 作为反向代理。

* [在 Ubuntu 14.04 LTS 上使用 Apache Web 服务器](https://www.linode.com/docs/websites/apache/apache-web-server-on-ubuntu-14-04)
说明了如何在 Ubuntu 14.04（现在仍然支持的版本） 上安装 Apache。然而需要注意的是，*不要* 安装 mod_python，因为它不再安全了，并且被 [mod\_wsgi 和 WSGI 服务器](/wsgi-servers.html) 隔离了。

* [使用 Virtualenv 和 mod\_wsgi 在 Apache 上部署 Django](http://thecodeship.com/deployment/deploy-django-apache-virtualenv-and-mod_wsgi/)
说明了在 Ubuntu 上要将带有 mod\_wsgi 的 Apache 设置好并运行起来需要安装哪些包。

* [Ubuntu 10.04 上的 Apache 和 mod\_wsgi](http://library.linode.com/web-servers/apache/mod-wsgi/ubuntu-10.04-lucid)
是一篇交旧 的文章，它说明了如何在不受支持的 Ubuntu 10.04 LTS 版本中设置 Apache。在 2016 年不推荐看这个设置，它已经过时了，但如果你正在使用 10.04 作为你的基础操作系统，你也许需要参阅这篇文章。
