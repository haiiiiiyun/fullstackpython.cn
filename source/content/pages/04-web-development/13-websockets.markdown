title: WebSockets
category: page
slug: websockets
sortorder: 0413
toc: False
sidebartitle: WebSockets
meta: WebSocket 是一种全双工 Web 通讯协议。到 Full Stack Python 上学习 WebSockets 知识。
updated: 2016-06-21 08:45


# WebSockets
WebSocket 是一种 [标准协议](http://tools.ietf.org/html/rfc6455)，用于在客户端和服务端之间进行双向数据传输。WebSockets 协议没有运行在 HTTP 之上，它是基于 [TCP](http://en.wikipedia.org/wiki/Transmission_Control_Protocol) 的一种独立实现。

## 为什么要用 WebSockets？
一个 WebSocket 连接允许在客户端和服务端之间进行全双工通讯，从而每一端都可以通过建立的连接向另一端推送数据。 WebSocket，以及与其相关的 [服务端发送事件](http://en.wikipedia.org/wiki/Server-sent_events) (SSE) 及 [WebRTC 数据通路](https://tools.ietf.org/html/draft-ietf-rtcweb-data-channel-12) 等技术之所以重要的原因是：HTTP不能打开并一直保持连接，不能在服务端和 Web 浏览器之间进行频繁的数据推送。在这之前，大多数的 Web 应用会通过频繁的异步 JavaScript 和 XML (AJAX) 请求来实现长轮循，如下图所示。

<img src="/img/ajax-long-polling.png" width="100%" alt="通过 AJAX 的长轮循对于一些应用来说相当的低效。" class="technical-diagram" />

服务端推送相比长轮循效率更高且更具扩展性，因为 Web 浏览器不再需要通过一系列的 AJAX 请求来持续地获取更新。

<img src="/img/websockets-flow.png" width="100%" alt="对于获取服务端所发送的更新来说，WebSocket 比 长轮循理有效率。" class="technical-diagram" />

虽然上图中所示的是服务端将数据推送给客户端，但是 WebSocket 是一个全双工的连接，因此客户端也能将数据推送给服务端，如下图所示。

<img src="/img/websockets-flow-with-client-push.png" width="100%" alt="WebSocket 也允许客户端向服务端推送数据。" class="technical-diagram" />

用 WebSockets 来获取服务端/客户端推送的更新，这种方式适合特定类型的 Web 应用，例如聊天室，这也是它之所以经常被用作 WebSocket 库的示例应用的原因。

## 实现 WebSocket
Web 浏览器和服务端都必须要实现 WebSocket 协议，以便建立和维护连接。因为 WebSocket 的连接是持续连通的，不像经典的 HTTP 连接，因此服务器需要做更多工作。

基于多线程或多进程的服务器不能很好地提供 WebSockets 服务，因为它们的设计是：打开一个连接，尽快处理完请求，然后关闭连接。因此，采用 [Tornado](http://www.tornadoweb.org/en/stable/) 或 打包了 [gevent](http://www.gevent.org/) 的 [Green Unicorn](http://gunicorn.org/) 等异步服务器，对于实现一个实用的服务端 WebSockets 都是必要的。 

而在客户端，使用 WebSocket 并不要求有某个 JavaScript 库。实现了 WebSocket 的 Web 浏览器都会通过 [WebSockets 对象](http://www.w3.org/TR/2011/WD-websockets-20110419/) 导出所有必要的客户端功能。

但是，JavaScript 封装库实现了优雅地降级（不支持 WebSocket 的情况下通常会采用长轮循机制），并隐藏了不同浏览器间的羞异，使用这些封闭库，会使开发者工作起来更加轻松。 有关 JavaScript 客户端库及 Python 实现的示例在下面列出。

## JavaScript 客户端库
* [Socket.io](http://socket.io/) 的客户端 JavaScript 库能与实现了 WebSocket 的服务端进行连接。

* [web-socket-js](https://github.com/gimite/web-socket-js) 是一个基于 Flash 的客户端 WebSocket 实现。

## Python 实现
* [Autobahn](http://autobahn.ws/python/) 使用 Twisted 或 asyncio 来实现 WebSocket 协议。

* [Crossbar.io](http://crossbar.io/) 构建于 Autobahn 之上，并且包含一个独立的服务器， 如果 Web 应用开发者需要的话，可以用它来对 WebSocket 连接进行单独处理。

## Nginx WebSocket 代理
Nginx 从 [第 1.3 版](http://nginx.com/blog/websocket-nginx/) 开始就正式支持 WebSocket 代理了，通过配置 Upgrade 和 Connection 头可以确保请求通过 Nginx 并到达你的 WSGI 服务器。第一次设置可能会有一点难度。

下面是我的 WebSockets 代理的 Nginx 配置。

    # this is where my WSGI server sits answering only on localhost
    # usually this is Gunicorn monkey patched with gevent
    upstream app_server_wsgiapp {
      server localhost:5000 fail_timeout=0;
    }

    server {

      # typical web server configuration goes here

      # this section is specific to the WebSockets proxying
      location /socket.io {
        proxy_pass http://app_server_wsgiapp/socket.io;
        proxy_redirect off;

        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;

        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection "upgrade";
        proxy_read_timeout 600;
      }
    }

值得注意的是，如何上面的示例配置不能工作，你应该查看 [官方的 HTTP 代理模块文档](http://nginx.org/en/docs/http/ngx_http_proxy_module.html)。

下面的这些资源对于正确的配置也很有帮助。

* Nginx 上有[与 WebSocket 代理相关的官方页面](http://nginx.org/en/docs/http/websocket.html)。

* [Nginx 中的 WebSockets](http://blog.martinfjordvald.com/2013/02/websockets-in-nginx/) 历数了 Nginx WebSockets 的配置指令。

* [用 Nginx 代理 WebSockets](https://chrislea.com/2013/02/23/proxying-websockets-with-nginx/) 展示了如何通过 Socket.io 进行代理。


## 使用 WebSockets 的开源 Python 示例
  [python-websockets-example](https://github.com/makaimc/python-websockets-example) 包含了创建一个简单 Web 应用的代码，它使用 Flash、Flask-SocketIO 和 gevent 来提供 WebSockets。

* Flask-SocketIO 项目中有一个 [聊天室 Web 应用](https://github.com/miguelgrinberg/Flask-SocketIO/tree/master/example)，演示了如何发送服务端生成的事件，以及如何通过表单的文本输入框来获取用户输入。

## 通用 WebSocket 资源
* 官方的 W3C [WebSockets API 候选草案](http://www.w3.org/TR/websockets/) 和 [WebSockets 工作草案](http://dev.w3.org/html5/websockets/) 都是不错的参考材料，但是对于刚接触 WebSockets 概念的开发者来说会有点难度。我建议先看下面列出的一些对初学者来说较容易的资料，然后再读那份工作草案。

* 由 Armin Ronacher 写的 [WebSockets 101](http://lucumr.pocoo.org/2012/9/24/websockets-101/) 提供了一份有关 HTTP 代理对 WebSockets 低水平支持的详细评估报告。同时对 WebSockets 协议的复杂性及其实现也进行了探讨。

* "我能使用吗？" 网站上有一份 [非常有用的 WebSockets 参照表](http://caniuse.com/#feat=websockets)，指出了哪些浏览器及其版本支持 WebSockets。

* Mozilla 的 [WebSockets 开发者资源](https://developer.mozilla.org/en-US/docs/WebSockets) 是一个查找 WebSockets 开发相关文档与工具的好地方。

* [从零开始学 WebSockets](https://blog.pusher.com/websockets-from-scratch/) 先对该协议进行了概述，然后对 WebSockets 的低层知识进行了讲解，这些知识对于只使用 Socket.IO 等库的开发人员来说通常是个黑盒子。

* [websocketd](http://websocketd.com/) 是一个 WebSockets 服务程序，意在成为 "WebSockets 的 CGI"。值得一看。


## Python 相关的 WebSockets 资源
* 我在 2015 年 1月份的 San Francisco Python 上的演讲中提到了 "[使用 WebSockets & gevent 实现异步 Python Web Apps](https://youtu.be/L5YQbNrFfyw)"，它是一个实时编写的 Flask Web 示例应用，如我创建的应用所示，它可以让用户通过 Websockets 实现互动。

* [Python 的实时操作](http://mrjoes.github.io/2013/06/21/python-realtime.html) 提供了 Python 相关的背景知识，叙述了在 Python 中过去是如何实现服务端更新推送的，以及随着 Python 工具的发展，现在是如何执行服务端更新的。

* [websockets](https://github.com/aaugustin/websockets) 是一个基于 Python 3.3+ 的 WebSockets 实现，它使用了 [asyncio](https://docs.python.org/3.4/library/asyncio.html) 模块 ( 如果你使用的是 Python 3.3 的话，是 [Tulip](https://code.google.com/p/tulip/) )。

* [交互式的演示文稿](https://www.twilio.com/blog/2014/11/choose-your-own-adventure-presentations-with-reveal-js-python-and-websockets.html) 这篇教程在服务端通过 gevent 实现 WebSockets，并使用 socketio.js 将投票数从服务端推送x给客户端。

* [为 Django 应用增加实时功能](http://crossbar.io/docs/Adding-Real-Time-to-Django-Applications/) 讲解了如何使用 Django 和 Crossbar.io 在应用中实现发布/订阅功能。

* [异步 Bottle](http://bottlepy.org/docs/dev/async.html) 讲解了在 Bottle Web 框架中如何使用 greenlets 来支持 WebSockets。

* 如果你部署到 Heroku 的话, 这里的这篇 [WebSockets 相关指南](https://devcenter.heroku.com/articles/python-websockets) 能帮助你部署你的 Python 应用。

* [Reddit 上的相关页面](http://www.reddit.com/r/Python/comments/2ujqd7/an_overview_of_using_websockets_in_python/) 有一些很有意思的评论，填补了我上面缺失的一点内容。

* [用 Python 和 Websockets 创建聊天室应用](http://pawelmhm.github.io/python/websockets/2016/01/02/playing-with-websockets.html) 展示了处理服务端 Websockets 连接的 Twisted 服务器代码及客户端的 JavaScript 代码。

* [使用 Websockets 实现 Flask 应用的客户端同步](http://www.matthieuamiguet.ch/blog/synchronize-clients-flask-application-websockets) 这份简短的教程，讲解了如何使用 Flask、Flask-SocketIO 扩展和 Socket.IO 实现在各浏览器客户端间更新数据。

* [WebSockets 能和 HTTP/2 共存吗？](http://www.infoq.com/articles/websocket-and-http2-coexist) 先对这两个协议进行了对比，然后阐述了它们之间的差异可能会导致 WebSockets 会被使用更长时间。
