title: Django
category: page
slug: django
sortorder: 0403
toc: False
sidebartitle: Django
meta: 在 Full Stack Python 上学习更多 Django 知识， Django 是一个流行的且功能完备的 Python Web 框架。
authors: haiiiiiyun.github.io
updated: 2016-06-12 08:27


# Django
[Django](http://www.djangoproject.com/) 是一个广为使用的 Python Web 应用框架，它奉行 “包含一切” 的哲学。该理念即为：创建 Web 应用所需的通用功能都应该包含到框架中，而不应存在于独立的软件包中。 

<a href="http://www.djangoproject.com/" style="border: none;"><img src="/img/django-logo-positive.png" width="100%" alt="Official Django logo. Trademark Django Software Foundation." class="technical-diagram" /></a>

例如，[身份验证](https://docs.djangoproject.com/en/dev/topics/auth/)、 [URL 路由](https://docs.djangoproject.com/en/dev/topics/http/urls/)、 [模板系统](https://docs.djangoproject.com/en/dev/topics/templates/)、 [对象关系映射](/object-relational-mappers-orms.html) (ORM) 和 [数据库迁移](https://docs.djangoproject.com/en/dev/topics/migrations/) (版本 1.7) 等功能都已包含在 [Django 框架](https://pypi.python.org/pypi/Django/) 中。 Flask 框架与 Django 相比，并没有包含这么多的功能，例如它还需要一个独立的 [Flask-Login](https://flask-login.readthedocs.org/en/latest/) 库来实现用户身份验证。

包含一切和易扩展性是实现框架时采用的两种不同哲学罢了，再两种方式各有千秋，不能说哪一种会再好。

<div class="well see-also">Django 是对<a href="/web-frameworks.html">Web 框架</a> 概念的一种实现。在 <a href="/web-development.html">Web 开发</a> 那一章你可以框架的各部分组件是如何协同工作的，或者到 <a href="/table-of-contents.html">总目录</a> 页去查看其它所有主题。</div>

## 为什么说 Django Web 框架是一个不错的选择
自创建以来， Django 项目的稳定性、高性能和它的社区在过去的十年中有了长足的发展。现在已经有大量的在线资源和图书资料，从中你能找到详细的教程和实践指南。该框架还在不断地往新版本中增加诸如 [数据迁移](https://docs.djangoproject.com/en/dev/topics/migrations/) 新功能。

我非常推荐 Python Web 开发新手使用 Django 框架，因为它的官方文档和一些教程的质量在软件开发界都是数一数二的。许多城市都有 Django 团体，如 [Django District](http://www.meetup.com/django-district/)、 [Django Boston](http://www.meetup.com/djangoboston/) 和 [San Francisco Django](http://www.meetup.com/The-San-Francisco-Django-Meetup-Group/)，因此新手在碰到难题时能获得帮助。

虽然有 [通过使用 Django 来学习 Python 是不好的](http://www.jeffknupp.com/blog/2012/12/11/learning-python-via-django-considered-harmful/) 这样的争议。但是，对于先前已经花时间学过 Python 语法和语义，然后才转入 Web 开发的人来说，这样的说法是站不住脚的。

## Django 图书和教程
已经有大量的免费或低价的 Django 资源。不过 Django 是在 10 年前发布的，并且之后又进行了大量的更新，因此当你要找一本与时俱进的 Django 图书时，应该先看看下面的这份列表，或者读下这篇文章 [当前的 Django 图书](http://twoscoopspress.org/pages/current-django-books)，截止到 Django 1.8，1.9。

* [Python 测试驱动开发](http://www.obeythetestinggoat.com/) 着重讲解如何用 Django 和 JavaScript 进行 Web 开发。该书将 Django 作为网站开发框架，并以一个实际案例的开发为例，讲解了如何进行测试驱动开发（TDD）。它的内容还涉及到 NoSQL、 Websocket 和异步响应等。该书能在网上免费阅读，或者你也可以购买 O'Reilly 的纸质版本。

* [和 Django 跳探戈](http://www.tangowithdjango.com/book17/) 上有一系列内容丰富的免费文章，介绍如何使用这个最受欢迎的 Python Web 框架。 现在很多开发人员都说这份资料对于他们克服刚开始学习框架时的困难很有帮助。这份资料最近已更新到 Django 1.7！

* [Django 宅女教程](http://tutorial.djangogirls.org/en/index.html) 是一份不错的教程，它能帮助你创建你的首个 Web 应用，并且不要求你之前有任何 Python 或 Django 相关知识。

* 由 Daniel Greenfeld 和 Audrey Roy 写的 [2 Scoops of Django](http://twoscoopspress.com/products/two-scoops-of-django-1-8) 对于真正想学好如何正确开发 Django 网站的人来说物有所值。

* [高效 Django](http://effectivedjango.com/) 是另一份介绍 Web 框架的免费资料。

* [Django subreddit](http://www.reddit.com/r/django) 上经常会有与 Django 学习相关的最新链接，并且那里也是个提 Django 问题的好地方。

* Steve Losh 写了一篇详实精彩的文章 [Django 忠告指南](http://stevelosh.com/blog/2011/06/django-advice/)。

* [轻量化 Django](http://programming.oreilly.com/2014/04/simplifying-django.html) 上有一些不错的示例，详述如何将 Django 分解成一些更小的组件。

* [Django 部署权威指南](https://github.com/rogueleaderr/definitive_guide_to_django_deployment) 对配置后的结构进行讲解，并包含一个自动化部署的 Chef 脚本。

* [将 Django 应用部署到 Amazon EC2 上](http://agiliq.com/blog/2014/08/deploying-a-django-app-on-amazon-ec2-instance/) 通过一个例子详实地演示了如果将一个 Django 应用部署到 Amazon Web 服务上。

* [Django 分步指南](http://aliteralmind.wordpress.com/2014/09/21/jquery_django_tutorial/) 展示了如何在 JQuery 中通过 AJAX 传输数据。

* [django-awesome](https://github.com/rosarior/awesome-django) 是一份精心整理的 Django 库和资源的列表。

* [开始一个 Django 项目](https://realpython.com/learn/start-django/) 解答了这个问题：“我如何从零开始配置一个 Django (1.5, 1.6, 1.7, or 1.8) 项目？”。

* 这份 Django 教程讲解了 [如何使用 Twitter Bootstrap、 Bower、 Requests 和 Github API 从零开始创建一个项目](http://drksephy.github.io/2015/07/16/django/)。

* [推荐的 Django 项目布局](http://www.revsys.com/blog/2014/nov/21/recommended-django-project-layout/) 能帮助 Django 开发新手理解项目中每个App的目录和文件是如何组织的。

* [Django 整合 Python 社交认证教程](https://github.com/davisfreeman1015/SocialAuthDjangoTutorial) 向你展示了如何在你的 Django 应用中集成社交媒体登录按钮。

* 由 Luke Plant 所写的 [他自己的基于类的视图的另一种方法](http://lukeplant.me.uk/blog/posts/my-approach-to-class-based-views/) (CBVs)这篇文章，经常会在 Django 社区中激起关于 CBV 是否能节省时间或者对于框架来说它是否”太过神奇“等的热烈争论。

* [如何在 Ubuntu 14.04 上使用 uWSGI 和 Nginx 部署 Django 应用](https://www.digitalocean.com/community/tutorials/how-to-serve-django-applications-with-uwsgi-and-nginx-on-ubuntu-14-04) 及 [如何设置 Django 、 PostgreSQL、 Nginx 和 Gunicorn](https://www.digitalocean.com/community/tutorials/how-to-set-up-django-with-postgres-nginx-and-gunicorn-on-centos-7) 这两个教程，详细演示了部署过程中的每个步骤。

* 每个 Web 应用都应处理好时区问题。这篇 [发布在 pytz and Django 上的文章](http://tommikaikkonen.github.io/timezones/) 对于你需要为此了解哪些知识给你指明了方向。

## Django 视频资源
除了文章，你还想找 Django 视频吗？在 [最佳 Python 视频](/best-python-videos.html) 页上有一节专门针对 Django 和 Web 开发的。


## Django 迁移
* Paul Hallett 发布在 Twilio 博客上的文章 [Django 1.7 应用升级详细指南](https://www.twilio.com/blog/2014/10/upgrading-your-django-reusable-app-to-support-django-1-7.html) 讲述了他对 django-twilio 包的使用经验。

* Real Python 上的 [迁移入门教程](https://realpython.com/blog/python/django-migrations-a-primer/) 探讨了 South 与 Django 内置的迁移功能之间的区别，并介绍了它们的使用方法。

* Andrew Pinkham 写的 ”升级到 Django 1.7“ 系列文章是很好的学习材料，据此你能了解该版本主要进行了哪些更新，以及能学到应如何相应地对你的 Django 项目进行更新。 [第 1 部分](http://andrewsforge.com/article/upgrading-django-to-17/part-1-introduction-and-django-releases/)、 [第 2 部分](http://andrewsforge.com/article/upgrading-django-to-17/part-2-migrations-in-django-16-and-17/)、 [第 3 部分](http://andrewsforge.com/article/upgrading-django-to-17/part-3-django-17-new-features/) 和 [第 4 部分](http://andrewsforge.com/article/upgrading-django-to-17/part-4-upgrade-strategies/) 现在都能找到。

* [不下线迁移 Django ](http://pankrat.github.io/2015/django-migrations-without-downtimes/) 展示了如何在 Django 站点不下线的情况下进行数据迁移。


## 1.9+ 中的通道
通道是 Django 1.9 的一种新机制(作为一个独立应用，稍后会合并到核心框架中），它能基于 [WebSocket](/websockets.html) 实现浏览器与服务器之间的实时双向通讯。
  
* [这份教程展示了如何在你的项目中引入 Django 通道功能](https://blog.heroku.com/archives/2016/3/17/in_deep_with_django_channels_the_future_of_real_time_apps_in_django)。

* [这个通道示例代码库](https://github.com/andrewgodwin/channels-examples) 里有一些不错的初始项目，如实时博客和聊天应用等，可以用作你的基础代码。

* 通道目前使用 Django 现有的认证机制，但是这篇文章 [在 Django 通道中使用 JSON Web Tokens 认证](http://www.machinalis.com/blog/jwt-django-channels/) 展示了如何在 Django 通道中使用第三方的 [JSON Web Token (JWT)](https://jwt.io/) 进行实现。


## Django 测试
* [Django 集成前端工具](https://lincolnloop.com/blog/integrating-front-end-tools-your-django-project/) 这篇文章指出了如何在开发环境或生产环境的 Django 网站上使用 [Gulp](http://gulpjs.com/) 来处理前端工具。

* [开始 Django 测试](http://howchoo.com/g/mjkwmtu5zdl/getting-started-with-django-testing) 将使你不再耽搁你的 Django 项目测试计划，如何你之前不知从何开始测试的话。

* [Django 测试](https://realpython.com/blog/python/testing-in-django-part-1-best-practices-and-examples/) 提供了大量的示例，并据此讲解如何对你的 Django 项目代码进行测试。

* [使用 Selenium 对 Django 视图进行自动化测试](https://medium.com/@unary/django-views-automated-testing-with-selenium-d9df95bdc926) 使用了一些示例代码来演示如何在浏览器里使用 [Selenium](http://www.seleniumhq.org) 进行测试。


## Django 及 Angular (Djangular) 资源
* [Django Rest 框架与 AngularJS 入门](http://blog.kevinastone.com/getting-started-with-django-rest-framework-and-angularjs.html) 是一篇有关 Djangular 的详细介绍，并附带示例代码。

* [用 Django 和 AngularJS 创建 Web 应用](https://thinkster.io/brewer/angular-django-tutorial/) 是一篇非常详实的指南，讲述如何以 Django 作为 API 层以及将 AngularJS 作为浏览器 MVC 前端进行开发。

* 这篇教程 [用 Django-Rest 框架 & AngularJS 进行 Web 应用开发，第 1 部分](http://mourafiq.com/2013/07/01/end-to-end-web-app-with-django-angular-1.html) 以及其 [第 2 部分](http://mourafiq.com/2013/07/15/end-to-end-web-app-with-django-angular-2.html)、 [第 3 部分](http://mourafiq.com/2013/08/01/end-to-end-web-app-with-django-angular-3.html) 和 [第 4 部分](http://mourafiq.com/2013/08/15/end-to-end-web-app-with-django-angular-4.html) 讲述了如何用 Djangular 创建一个示例博客系统。该项目的代码存放在 [GitHub 上](https://github.com/mouradmourafiq/django-angular-blog)。

* [Django-angular](https://github.com/jrief/django-angular) 这个代码库意在使 Django 和 AngularJS 在前端开发上更匹配。


## Django ORM 资源
Django 有自己内置的的对象关系映射器(ORM), 通常指代为 "the Django ORM"。到 [Python 对象关系映射页](/object-relational-mappers-orms.html) 上了解 Django ORM 相关的更多信息，那上面有一节是专门解读 Django ORM的，当然上面还有其它的资源和教程。

## 静态和媒体文件
Django 初级开发人员对于如何部署和处理静态和媒体文件会感觉困惑。下面列出的资料以及 [静态内容](/static-content.html) 那一页上的资源对于搞清楚如何正确处理这些文件很有帮助。

* [使用 Amazon S3 来存储你的 Django 站点静态和媒体文件](http://www.caktusgroup.com/blog/2014/11/10/Using-Amazon-S3-to-store-your-Django-sites-static-and-media-files/) 是一篇很好的文章，解答了如何部署静态和媒体文件这个通常被问到的问题。

* [从文件系统中导入 Django FileField 和 ImageFields](http://www.revsys.com/blog/2014/dec/03/loading-django-files-from-code/) 向你展示了数据模型的文件类型的项值是如何从文件系统中导入的。

* [在 Django 中限制对用户上传的文件的访问](http://blog.wearefarm.com/2015/02/09/contact-form-uploads/) 提供了对媒体文件的一种保护机制。


## 开源 Django 示例项目
* [使用 Django 和 Twilio 制作浏览器通话器](https://www.twilio.com/docs/howto/walkthrough/browser-calls/python/django) 展示了如何利用 Django 和 [Twilio 客户端](https://www.twilio.com/client) 来创建一个 Web 应用，将用户的浏览器改造成一个全功能的电话机。非常有趣。

* [Txt 2 React](https://github.com/makaimc/txt2react) 是一个 Django Web 应用，它能让观众一边观看演示，一边输入反馈信息或者提问。

* [Openduty](https://github.com/ustream/openduty) 是一个网站状态检查和报警系统，类似于 PagerDuty。

* [Courtside](https://github.com/myusuf3/courtside) 是一个收集体育活动信息的 Web 应用，由 PyCoder‘s Weekly 的作者编写和维护。

* Django 交互式语音应答系统 (IVR)，它的两份 Web 应用代码库： [第 1 部分](https://github.com/phalt/twilio-django-part-1) 和 [第 2 部分](https://github.com/phalt/twilio-django-part-2) 向你展示了如何创建一个真正有趣的 Django 应用 。它还有相应的 [文章](https://www.twilio.com/blog/2014/07/build-an-ivr-system-with-twilio-and-django.html)， 对其中的每一个步骤进行了详细的讲解。

* [Taiga](https://github.com/taigaio/taiga-back) 是一个项目管理工具，后端用 Django 开发，前端用 AngularJS 开发。


## Django 项目模板
* [Caktus Group Django 项目模板](https://github.com/caktus/django-project-template) 适用于 Django 1.6+。

* [Cookiecutter Django](https://github.com/pydanny/cookiecutter-django) 这个项目模板出自 Daniel Greenfeld，它使用了 Audrey Roy 的 [Cookiecutter](https://github.com/audreyr/cookiecutter)。使用该模板的项目部署到 Heroku 上非常容易。

* [Two Scoops Django 项目模板](https://github.com/twoscoops/django-twoscoops-project) 同样来自 PyDanny 和 Audrey Roy。这个模板提供了一个在《Two Scoops of Django》那本书中描述过的快速代码框架。

* [Sugardough](https://github.com/mozilla/sugardough) 这个 Django 项目模板来自 Mozilla，并与 cookiecutter 兼容。


## Django 学习清单
1. 在你的本地开发机器上 [安装 Django](https://docs.djangoproject.com/en/dev/topics/install/)。

1. 依据 ["polls" 这个教程](https://docs.djangoproject.com/en/dev/intro/tutorial01/)进行练习。
 
1. 依据 “Django 资源” 那一节上的相关教程，创建一些简单的应用。

1. 参考 [官方文档](https://docs.djangoproject.com/en/dev/) 以及上面的资源链接，开始编写你自己的 Django 项目。当然你会犯错误，但这是你学习如何正确的创建应用的必经之路。

1. 阅读 [2 Scoops of Django](http://www.amazon.com/Two-Scoops-Django-Best-Practices/dp/0981467342) 来理解 Django 的最佳实践，并学会什么是创建 Django Web 应用的更好方式。

1. 查看 [部署那一章](/deployment.html)，将你的 Django 项目发布到网上。
