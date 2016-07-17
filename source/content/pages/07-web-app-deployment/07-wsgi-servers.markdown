title: WSGI 服务器
category: page
slug: wsgi-servers
sortorder: 0707
toc: False
sidebartitle: WSGI 服务器
meta: 通过在一个 web 服务器网关接口（WSGI）服务器上运行 Python 代码来创建 web 应用。快来 Full Stack Python 学习更多有关 WSGI 服务器的知识吧。
translators: blog.chriscabin.com
updated: 2016-07-14 08:40


# WSGI 服务器
[Web 服务器网关接口](http://wsgi.readthedocs.org/en/latest/)
(WSGI) 服务器通过实现 web 服务器一侧的 WSGI 接口来运行 Python web 应用。


## 为何 WSGI 是必要的？
传统的 web 服务器并不懂得或者没有任何方法来运行 Python 应用。 在 1990 年代晚期，一位名叫 Grisha Trubetskoy 的人
[开发了一个叫做 mod\_python 的 Apache 模块](http://grisha.org/blog/2013/10/25/mod-python-the-long-story/) 
来运行任意的 Python 代码。在 1990 年代晚期的几年以及 2000 年代早期，配置了 mod\_python 模块的 Apache 服务器运行着大多数的 Python web 应用。

然而，mod\_python 并非标准规范。它仅仅是一个允许在服务器上运行 Python 代码的实现而已。随着 mod\_python 开发渐缓并且有不少安全漏洞被发现，社区开始意识到，需要一种运行 Python web 应用的一致性方法。
 
因此，Python 社区提出了将 WSGI 作为一个标准接口规范，来实现各种模块和容器。如今，WSGI 已经是用来运行 Python web 应用的公认方法了。

<img src="/img/wsgi-interface.png" alt="WSGI server invoking a WSGI application." width="100%" class="technical-diagram" />

如上图所示，正如 PEP 3333 标准所定义的那样，WSGI 服务器只是简单地调用一个 WSGI 应用的可调用对象。


## WSGI 的目的
为什么要使用 WSGI？而不仅仅是在应用中直接指定一个 web 服务器？

* **WSGI 为你提供了灵活性**。应用开发者们可以使用其它组件来替换 web 堆栈中相应组件。例如，开发者可以轻易地从 Green Unicorn 切换到 uWSGI，而不用修改实现了 [PEP 3333](http://www.python.org/dev/peps/pep-3333/) 标准定义的 WSGI 的应用或框架：

    在 Python 的 web 服务器中广泛使用这种 API [...] 可以将框架的选择和 web 服务器的选择分开，可以让用户自由地选择适合他们的一对框架和 web 服务器，同时也让框架开发者和服务器开发者们自由地分别聚焦在他们所擅长的特殊领域中。

* **WSGI 服务器增强了扩展性**。同时提供上千次针对动态内容的请求服务是 WSGI 服务器的责任，而非框架的责任。WSGI 服务器处理来自 web 服务器的请求，并决定如何让这些请求和应用框架进程通信。责任的分离对于有效地扩展 web 流量是非常重要的。

<img src="/img/web-browser-server-wsgi.png" alt="WSGI Server - Web server - Browser" width="100%" class="technical-diagram" />

WSGI 的设计宗旨就是为运行 Python 代码提供简单的标准接口。作为一名 web 开发者，你没有必要了解更多下面列出的知识：

* WSGI 代表什么（Web 服务器网关接口）

* WSGI 容器是一个分离运行的进程，并且运行在一个不同于你的 web 服务器的端口上

* 需要配置你的 web 服务器来给运行着你的 web 应用的 WSGI 容器传递请求，然后再将（HTML 形式）的响应传递回请求方

如果你正在使用一个标准的 web 框架，如 Django、Flask、或者 Bottle，亦或是任何当前存在的 Python 框架，你都不用担心框架是如何实现应用层一侧的 WSGI 标准的。类似地，如果你正在使用一个标准的 WSGI 容器，如 Green Unicorn、uWSGI、mod\_wsgi 或 gevent，你可以直接让它们运行，而不用担心它们是如何实现 WSGI 标准的。

然而，当你成为一名更加富有经验的 Python web 开发者后，你应当把了解 WSGI 标准以及那些框架和容器如何实现 WSGI 的知识加入到你的学习清单中。


## 官方 WSGI 规格说明
1.0 版本的 WSGI 标准在
[PEP 0333](http://www.python.org/dev/peps/pep-0333/) 中规定。到了 2010 年 9 月，
WSGI 1.0 版本被
[PEP 3333](http://www.python.org/dev/peps/pep-3333/) 定义的 WSGI 1.0.1 版本替代。如果你正在使用 Python 2.x 并且适应了 PEP 0333，那么你也会适应 PEP 3333。新的版本只是简单地为了支持 Python 3 而做的更新，并且还有如何处理 unicode 的说明。

[Python 2.x WSGI 资料](https://docs.python.org/2/library/wsgiref.html) and
[Python 3.x WSGI 资料](https://docs.python.org/3.4/library/wsgiref.html)
是内置在 Python 标准库中的 WSGI 规范实现的参考资料，从而来帮助你构建 WSGI 服务器和应用。


## Web 服务器配置样例
Web 服务器配置规定了什么样的请求应该交给 WSGI 服务器处理。一旦 WSGI 服务器产生并处理完请求后，响应就会被 web 服务器传送回浏览器。

例如，这个 Nginx web 服务器配置规定了 Nginx 应当处理在 /static 目录下的静态资源（如图片、JavaScript、和 CSS 文件）访问请求，并且将所有其他的请求传递给运行在 8000 端口上的 WSGI 服务器:

    # 这个配置表明有一个运行在 8000 端口上的 WSGI 服务器
    upstream app_server_djangoapp {
        server localhost:8000 fail_timeout=0;
    }

    # Nginx 配置为运行在标准HTTP端口上，并监听请求
    server {
      listen 80;

      # Nginx 应当为静态资源提供服务，并且永远不要把它交给 WSGI 服务器处理
      location /static {
        autoindex on;
        alias /srv/www/assets;
      }

      # 所有非针对 /static 目录的请求都会交给 WSGI
      # 服务器，即上面配置的运行在 8000 端口上服务器
      location / {
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_set_header Host $http_host;
        proxy_redirect off;

        if (!-f $request_filename) {
          proxy_pass http://app_server_djangoapp;
          break;
        }
      }
    }

需要注意的是，上面的Nginx 配置代码仅仅是准产品级的简化配置版本。对于真实使用了 SSL 和非 SSL 的模板，请参见 Github 上的
[Underwear web server templates](https://github.com/makaimc/underwear/tree/master/underwear/roles/web/templates)。


## WSGI 服务器
在
[WSGI 阅读文档](http://wsgi.readthedocs.org/en/latest/servers.html) 页面中有一个完整的 WSGI 服务器列表。
以下是社区推荐的 WSGI 服务器：

* [Green Unicorn](http://gunicorn.org/) 是一个采用了工作者模型的 WSGI 服务器，脱胎于 Ruby 的 [Unicorn](http://unicorn.bogomips.org/) 项目。

* [uWSGI](http://uwsgi-docs.readthedocs.org/en/latest/) 正在掀起浪潮，因为它是一款高性能的 WSGI 服务器实现。

* [mod\_wsgi](https://github.com/GrahamDumpleton/mod_wsgi) 是一个实现了 WSGI 规格的 Apache 模块。

* [CherryPy](https://github.com/cherrypy/cherrypy) 是一个纯粹的 Python web 服务器，并且也可以作为一个 WSGI 服务器。

## WSGI 资源
* [PEP 0333 WSGI v1.0](http://www.python.org/dev/peps/pep-0333/)
  和
  [PEP 3333 WSGI v1.0.1](http://www.python.org/dev/peps/pep-3333/)
  规格说明。

* 这篇文章 [WSGI 基础](http://agiliq.com/blog/2013/07/basics-wsgi/) 
  包含了一个简单的例子演示了一个 WSGI 兼容的应用是如何工作的。

* [针对 Python web 应用的 web 服务器对比](https://www.digitalocean.com/community/tutorials/a-comparison-of-web-servers-for-python-based-web-applications)
  是一篇非常好的阅读材料，可以帮助你理解不同的 WSGI 服务器实现的基础知识。

* "[完全单服务器 Django 栈教程](http://www.apreche.net/complete-single-server-django-stack-tutorial/)" 中有一篇详细讲解了如何使用 LAMP 栈托管网站的文章。

* Python 社区花费了很大的努力才
  [从 mod\_python 转移](http://blog.dscpl.com.au/2010/05/modpython-project-soon-to-be-officially.html) 
  到 WSGI 标准。那个转移周期现在已经完成了，并且总应该使用 WSGI 实现来代替 mod\_python。 

* Nicholas Piël 写了一篇非常有趣的文章给
  [Python WSGI 服务器](http://nichol.as/benchmark-of-python-web-servers) 评分。
  注意，那篇文章已经有些旧了。评分只是由它们在特定的测试场景下得出的，并不能由此快速地推断出“这个服务器比其它服务器更快”的结论。

* [如何使用 CherryPy 部署 Python WSGI 应用](https://www.digitalocean.com/community/articles/how-to-deploy-python-wsgi-applications-using-a-cherrypy-web-server-behind-nginx)
  回答了为何 CherryPy 是一个简单的 web 和 WSGI 服务器的组合，同时给出了如何使用它的方法。

* 另外一篇由“数字海洋（Digital Ocean）”推出的演练教程讲解了
  [如何使用 Gunicorn HTTP 服务器部署 Python WSGI 应用，并在背后使用 Nginx 服务器](https://www.digitalocean.com/community/tutorials/how-to-deploy-python-wsgi-apps-using-gunicorn-http-server-behind-nginx).

* [uWSGI 瑞士军刀](https://lincolnloop.com/blog/uwsgi-swiss-army-knife/) 说明了 uWSGI 在部署中是如何做到不仅能运行 Python web 应用，而且还可以提供静态文件访问服务以及处理缓存的。


## WSGI 服务器学习清单
1. 理解 WSGI 是一个需要应用和服务器实现的 Python 标准规范。

1. 根据可用的文档和教程选择一个 WSGI 服务器。Green Unicorn 就是非常好的起点，因为它已经出现有段时间了。

1. 在你的服务器部署中添加 WSGI 服务器。

1. 配置 web 服务器给 WSGI 服务器传递符合适当 URL 模式的请求。

1. 测试你的 WSGI 服务器响应本地的请求，而不是来自你的设备以外的直接请求。Web 服务器应当能够向 WSGI 服务器传递请求并从那儿获得响应。

