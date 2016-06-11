title: Web 框架
category: page
slug: web-frameworks
sortorder: 0402
toc: False
sidebartitle: Web 框架
meta: 了解 Python Web 框架--解决 Web 应用创建中的通用难题的代码库。
authors: haiiiiiyun.github.io
updated: 2016-06-11 09:30


# Web 框架
Web 框架就是一份代码库，它能帮助开发人员创建可靠、可扩展、易维护的 Web 应用。

## 为什么 Web 框架很有必要？
Web 框架封装了开发人员在过去二十年中学到的网站和 Web 应用开发的经验总结。它使得重用代码（例如通用 HTTP 操作和项目代码组织等）变得更加容易，因而熟悉该框架的其他开发人员就能快速创建和维护应用程序。

## Web 框架的基本功能
框架通过它们自己的代码或扩展代码提供功能，以实现运行 Web 应用所需的基本操作。这些基本操作包括：

1. URL 路由
2. HTML、 XML、JSON 及其它输出模式模板
3. 数据库处理
4. 跨站请求伪造安全问题（CSRF）和其它攻击
5. session 存取

不是所有的 Web 框架都包含以上全部功能。框架种类从执行单一的用例到提供每个开发人员熟知的每个 Web 框架功能，不一而足。一些框架奉行“即插即用”的理念，把所有可能的东西都打包进来，而其它一些框架却有一个很小的内核包，以方便通过第三方代码包来扩展功能。

例如，[Django Web 应用框架](/django.html) 含有一个对象关系映射 (ORM) 层来对关系型数据库的读、写、查询和删除操作进行抽象。但是，Django 的 ORM 如果不进行大量修改的话，是不能操作像 [MongoDB](http://www.mongodb.org/) 等的非关系型数据库的。

其它一些框架，像 [Flask](/flask.html) 和 [Pyramid](/pyramid.html) 可以通过包含进外部 Python 库来更加容易地与非关系型数据库一起使用。框架的实现，都需要在最少功能和易扩展性，以及将所有东西都包含进来以提高整合度这两个选择之间进行抉择。

## Web 框架对比
你对一个项目用 Django 实现和用 Flask 实现的代码对比感兴趣吗？看下 [这篇 Django Web 应用教程](https://www.twilio.com/docs/howto/walkthrough/appointment-reminders/python/django) 然后再看下 [由 Flask 实现的相同的应用](https://www.twilio.com/docs/howto/walkthrough/appointment-reminders/python/flask)。

还有一份代码库叫 [compare-python-web-frameworks](https://github.com/makaimc/compare-python-web-frameworks)，上面的一个相同的 Web 应用由不能的 Python Web 框架、模板引擎和 [对象关系映射器](/object-relational-mappers-orms.html)来实现。


<div class="well see-also">既然已经学了 Web 框架，你也应该学下 <a href="/deployment.html">Web 应用部署</a> 和 <a href="/application-programming-interfaces.html">Web API</a>。</div>


## 我需要使用 Web 框架吗？
你的项目是否需要使用 Web 框架取决于你的网站开发经验和你的目标。如果你是一个初级程序员并且以学习为目的来开发一个 Web 应用，那么框架能帮助你理解下面的这些概念，例如 URL 路由、数据处理和认证等这些主流的 Web 应用都具有的功能。

另一方面，如果你是一位有经验的程序员，具有丰富的网站开发经验，你可能会觉得现有的框架不能满足你的项目需求。如果那样的话，你可以将 [Werkzeug](http://werkzeug.pocoo.org/) 等开源库、WSGI 功能包和你自己的代码进行混合匹配来创建你自己的框架。 Python 的生态系统仍然为新框架留了足够的空间，以便去满足那些不能从[Django](/django.html)、 [Flask](/flask.html)、 [Pyramid](/pyramid.html)、 [Bottle](/bottle.html) 和 [许多其它框架](/other-web-frameworks.html) 中得到满足的程序员的需求。

简言之，你是否需要使用 Web 框架来创建 Web 应用取决于你的经验和你的目标。使用框架来创建 Web 应用当然不是必需的，但是在多数情况下，它能让开发人员的生活变得更加轻松。

## Web 框架相关资源
* "[什么是 Web 框架？](http://www.jeffknupp.com/blog/2014/03/03/what-is-a-web-framework/)" 深入讲解了什么是 Web 框架以及它们与 Web 服务器的关系。

* 你可以看下 Stack Overflow 上有关 "[什么是 Web 框架以及如何与 LAMP 比较？](http://stackoverflow.com/questions/4507506/what-is-a-web-framework-how-does-it-compare-with-lamp)" 这个问题的答案。

* [框架](http://youtu.be/W6KCPXl6Zuc) 真的是一部精彩的短视频，它向你讲解了如何选择 Web 框架。它的作者对一个框架应该有哪些功能有一些独特的看法。我赞同里面说的大部分内部，尽管我认为如果 session 和 数据库 ORM 如何实现的好的话也应该是框架的一个有用的构件。

* [Django vs Flask vs Pyramid：选择一个 Python Web 框架](https://www.airpair.com/python/posts/django-flask-pyramid) 包含了一些背景资料，并通过用这三个主流的 Python 框架实现类似的 Web 应用来进行代码对比。

* 这篇精彩的博文通过对代码的图形化分析，列出了 [几个 Python Web 框架的代码复杂度](http://grokcode.com/864/snakefooding-python-code-for-complexity-visualization/)。

* [Python Web 框架基准测试](http://klen.github.io/py-frameworks-bench/) 上有一份针对各框架响应度的测试，测试方式是先将一个对象编码成 JSON 然后返回，以及从数据库中读取数据然后在模板中呈现。虽然没有确凿性结果，但是看看上面的输出内容还是很有趣的。

* [你使用什么 Web 框架以及为什么觉得它好？](http://www.reddit.com/r/webdev/comments/2les4x/what_frameworks_do_you_use_and_why_are_they/) 是 Reddit 上有关 Web 框架的讨论。 看看使用其它语言的程序员对于他们的 Web 框架的品味，然后与主流的 Python 框架比较一下也是蛮有意思的。

* 这个由用户投票的问答网站上问到 "[在生产环境下哪个是最好的通用 Python Web 框架？](http://www.slant.co/topics/426/~what-are-the-best-general-purpose-python-web-frameworks-usable-in-production-sites)"。看看上面列出的那么多能让 Python 开发人员使用的框架比看投票结果重要多了。


## Web 框架学习清单
1. 选择一个主流 Python Web 框架 (推荐 [Django](/django.html) 和 [Flask](/flask.html))，然后坚持使用。刚开始的时候最好只学习一个框架，而不要试图去理解每个框架。

1. 根据那个框架的网站上的资源链接，寻找一份详细的教程，并据此进行练习。

1. 研究用你所选框架开发的开源案例，这样你就能参与这些项目并在你的应用中重用这些代码。

1. 写完你的 Web 应用的第一个版本，然后参考 [部署](/deployment.html) 那一章，将它发布到网上。

