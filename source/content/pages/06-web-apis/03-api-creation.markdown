title: API 的创建
category: page
slug: api-creation
sortorder: 0603
toc: False
sidebartitle: API 的创建
meta: Web API 使得机器间的交互成为可能。到 Full Stack Python 上学习更多关于创建 Web API 的知识。
authors: haiiiiiyun.github.io
updated: 2016-07-28 21:30--2016-08-18 22:49


# API 的创建
创建和分布 API 能使你的 Web 应用可以通过机器间的通信与其它应用进行交互。


## API 创建的相关框架

* [Django REST 框架](http://www.django-rest-framework.org/) 和 [Tastypie](https://django-tastypie.readthedocs.org/en/latest/) 是 Django 中两个最常用的 API 框架。 当前 Django REST 框架的功能由乱轰轰的社区情绪决定。由于 Tom Christie 在 [Kickstarter 上成功地募集到了资金](https://www.kickstarter.com/projects/tomchristie/django-rest-framework-3)，Django REST 框架在 [3.0 版本后](http://www.django-rest-framework.org/topics/3.0-announcement/) 还将有大的改进。

* [Flask-RESTful](http://flask-restful.readthedocs.org/en/latest/) 是 Flask 中常用于创建 Web API 的框架。它最先由 [Twilio 开源，并在一篇博客中进行了讲解](https://www.twilio.com/engineering/2012/10/18/open-sourcing-flask-restful)，然后又移交给了 [它自己的 GitHub 组织](https://github.com/flask-restful/flask-restful)，从而使得公司外部的工程师也可以成为核心贡献者。

* [Flask API](http://www.flaskapi.org/) 是另一个能从 Flask Web 应用中导出 API 的通用库。

* [Sandman](http://www.github.com/jeffknupp/sandman) 是一款广泛使用的工具，它能从旧数据中自动生成 RESTful API 服务，无需编写一行代码（虽然它很容易通过代码扩展）。

* [Cornice](https://cornice.readthedocs.org/en/latest/) 是 Pyramid 中的一个 REST 框架。

* [Restless](https://github.com/toastdriven/restless) 是一个轻量级的 API 框架，意在不关联任何框架。其基本理念是：只需很少的移植量，就能将相同的 API 代码用于 Django、 Flask、 Bottle、 Pyramid 或任何其它 WSGI 框架。

* [Eve](http://python-eve.org/) 是一个用 Flask、MongoDB 和 Redis 构建的 Python REST 框架。该框架的主要作者 [Nicola Iarocci](https://twitter.com/nicolaiarocci) 在 [EuroPython 2014](https://www.youtube.com/watch?v=9sUsLvG72_o) 作了一次精彩的演讲，并对该框架的主要功能特性进行了介绍。

* [Falcon](http://falconframework.org/) 是一个快速的轻量级框架，非常适合用于创建 RESTful API。

* [Hug](https://github.com/timothycrosley/hug) 基于 Falcon 和 Python3，它的目标是使开发 Python 驱动的 API 尽可能简单。它借助 Python3 的函数注释功能对进入和输出的 API 参数进行自动的验证和转换。

* [Pycnic](http://pycnic.nullism.com) 是一个以 REST 思想设计的纯 JSON-API 框架。

## API 测试框架
创建、运行和维护 API 与创建、运行和维护一个 Web 应用需要花费相同的精力。API 测试框架等同于 Web 应用中的浏览器测试框架。

* [zato-apitest](https://github.com/zatosource/zato-apitest) 能调用 HTTP API， 并提供能通过其它测试框架运行的回调挂勾。


## 托管的 API 测试服务
* [Runscope](https://www.runscope.com/) 是一款 API 测试 SaaS 应用，它对你自己的 API 和你的应用所依赖的外部 API 都能测试。

* [API Science](https://www.apiscience.com/) 专注于尝试 API 测试，包括多步 API 调用和外部 API 监测。

* [SmartBear](http://smartbear.com/api-testing/) 中有几款 API 监测和测试工具。


## API 创建相关资源

* [API 的好坏只由它的文档决定](https://rocketeer.be/blog/2015/03/api-quality/) 是 Web API 世界中的一个很强大的诅咒，很多 API 都因其低质量的文档而阻碍了它们的扩散使用。如果 API 没有很好的文档，那么开发人员一旦有其它的选择，就会忽略它。

* [运营一个免费、开放的 API 的冒险之举](http://www.cambus.net/adventures-in-running-a-free-public-api/) 讲述了一个简短的故事，一个开发者的 geolocation API 被滥用，但是他由于缺少相关资源从而不能阻止进一步的滥用。最终他只好关闭了免费计划，只提供付费计划，同时允许其他人根据他的开源代码提供服务。防范欺诈和恶意软件是一项艰巨的任务，因此要留心服务器的使用率和终端调用的增长量，从而将合法和非法流量区别出来。

* [API Doc JS](http://apidocjs.com/) 允许开发人员在他们的文档中嵌入标记，从而能根据其 API 中的端点生成网站。

* [开发人员为什么讨厌你的 API 的 10 个原因（及如果应对）](http://www.slideshare.net/jmusser/ten-reasons-developershateyourapi) 列数了开发人员在使用 API 时能面临的最主要的困难和烦恼，并给出了使你的 API 避免出现这种情况的举措。

* RESTful API 的版本控制在 Web API 社区中是一个困难及具争论的话题。这个包含两部分的系列文章涵盖了 [对你的 API 进行版本控制的各种方法](http://urthen.github.io/2013/05/09/ways-to-version-your-api/) 及 [如何设计一个无版本的 API](http://urthen.github.io/2013/05/16/ways-to-version-your-api-part-2/)。

* [NARWHL](http://www.narwhl.com/) 对于那些困惑于什么是适当的 RESTful API 的开发人员来说是一个很实用的 API 设计网站。

* [18F](https://18f.gsa.gov/) [的 API 标准](https://github.com/18f/api-standards) 讲解了他们创建现代化的 RESTful API 时所做的设计决策的背后细节。

* [设计一个优雅的 REST API](https://medium.com/@zwacky/design-a-beautiful-rest-api-901c73489458) 回顾了关于端点、版本、错误和分页等的通用设计决策。还有一个 [源材料 YouTube 视频](https://www.youtube.com/watch?v=5WXYw4J4QOU)，上面这篇博文中的建议内容就是源于该视频。

* [加快脚步，不要破坏你的 API](http://amberonrails.com/move-fast-dont-break-your-api/) 是来自 Stripe 的 Amber Feng 的幻灯片及详细的博文，讲述了创建一个 API，分隔责任层，隐藏向后兼容性和针对开发人员和 API 设计人员的其它大量的好建议。

* [自描述，不是的。不要假设任何事情。](http://www.bizcoder.com/self-descriptive-isn-t-don-t-assume-anything) 指出元数据对 API 是否具有描述性影响很大。

* [设计 Artsy API](http://artsy.github.io/blog/2014/09/12/designing-the-public-artsy-api/) 基于他们最近的经验，提出了创建 API 的建议列表。

* [一些 REST 的最佳实践](https://bourgeois.me/rest/) 是一份在创建 API 时需要遵循的高水准的规律总结。

* Hacker News 上有关于 [编写 API 规范的最佳方式是什么？](https://news.ycombinator.com/item?id=8912897) 的讨论，上面提出了一些关于该主题的不同的见解。

* [《Apigee 的 Web API 设计》](https://pages.apigee.com/rs/apigee/images/api-design-ebook-2012-03.pdf) 是一本免费的电子书，里面包含了关于如果设计你的 Web API 的丰富的实践建议。

* [REST API 中的 1-对-1 关系和子资源](http://developers.lyst.com/2015/02/20/1-to-1-relationships-and-subresources-in-rest-apis/) 讲述了 API 创建过程中所需做的设计决策以及如何做出这些选择的原因。

* [你的 API 到底需要多少个状态代码？](https://blogs.dropbox.com/developers/2015/04/how-many-http-status-codes-should-your-api-use/) 从一个 Dropbox API 开发者所做过的决策过程中获取了答案。

* 这份 [API 设计指南](https://github.com/interagent/http-api-design) 是 Heroku 为其平台的 API 所写的最佳实践。


## 针对 Python 的 API 创建相关资源

* 由 [PyDanny](https://twitter.com/pydanny) 写的 [为 Django 选择一个 API 框架](http://pydanny.com/choosing-an-api-framework-for-django.html) 这篇文章包含了什么是好的 API 框架以及当前应该为 Django 选择哪个框架等的问题与洞见。 

* [使用 Pyramid 和 Ramses 快速创建 REST API](https://realpython.com/blog/python/create-a-rest-api-in-minutes-with-pyramid-and-ramses/) 是份详尽的教程，它从头至尾使用 [Pyramid](/pyramid.html) Web 框架和 [Ramses](https://pypi.python.org/pypi/ramses/), --一个使用 YAML 文件来创建 REST API 的库。

* [Python 中的 RESTful Web 服务](http://www.slideshare.net/Solution4Future/python-restful-webservices-with-python-flask-and-django-solutions) 对 Python API 框架领域进行了有趣的概述。

* [使用 Python & Flask 实现一个 RESTful Web API](http://blog.luisrei.com/articles/flaskrest.html) 很好地演示了如何编写一个 Flask 应用，以提供标准的 Web API 功能，如适当的 HTTP 响应，认证和日志等。

* [REST Hooks](http://resthooks.org/) 是一个开源的 Python 项目，它使得实现一个基于订阅的 "REST hooks" 更加容易。REST hooks 和 webhooks 非常相似，但它提供了一种不同的机制，通过 REST 接口来订阅更新。 REST hooks 和 webhooks 相比于通过轮循来获取更新和通知，效率高得多。

* 序列化对于将对象转换成 Web API JSON 的结果是很常用的功能。有个公司发现 Django REST 框架的序列化性能不太好，为些创建了 [Serpy](https://github.com/clarkduvall/serpy) 并且 [为其性能结果专门写了一些博文](https://engineering.betterworks.com/2015/09/04/ditching-django-rest-framework-serializers-for-serpy/)。

* [创建更好的 API 文档](https://engineering.gosquared.com/building-better-api-docs) 展示了 Square 如何通过使用 Swagger 和 React 来创建更加有用的文档。


## Django REST 框架相关资源

* 这份包含多个部分的系列文章中的 [开始使用 Django REST 框架和 AngularJS (第 1 部分)](http://engineroom.trackmaven.com/blog/getting-started-drf-angularjs-part-1/) 及其 [第 2 部分](http://engineroom.trackmaven.com/blog/getting-started-drf-angularjs-part-2/) 很好地展示了一个 RESTful API 如何能为一个使用 JavaScript MVC 框架构建的客户前端提供后端服务。

* 如果你正在找一个可以用的 Django REST 框架项目示例，看下 [PokeAPI](https://github.com/phalt/pokeapi)，它在 BSD 许可下开源。


## API 创建的学习清单

1. 选择一款适合用于你的 Web 应用的 API 框架。Django 项目我推荐 Django REST 框架，Flask 项目我推荐 Flask-RESTful。

1. 首先为 API 构想出一个简单的使用案例。通常该使用案例要么是关于用户所需的机器可读格式的数据，要么是针对像 iOS 或 Android 移动应用等其它客户端的后端。

1. 通过 OAuth 或者一个令牌方案添加一个认证机制。

1. 为 API 增加使用限制，如何数据使用量会引起性能问题的话。还要加入基本的度量功能，从而能检测 API 的访问频度及其是否运行正常。

1. 提供丰富的文档及关于该 API 如何访问和使用的示例。

1. 想出其它的使用案例，并基于你从开始时的 API 使用案例中学到的知识进行扩展。
