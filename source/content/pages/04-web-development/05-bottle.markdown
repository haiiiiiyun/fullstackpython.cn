title: Bottle
category: page
slug: bottle
sortorder: 0405
toc: False
sidebartitle: Bottle
meta: Bottle 是一个单文件的 Python Web 框架。到 Full Stack Python 上了解有关 Bottle 的更多知识。
authors: haiiiiiyun.github.io
updated: 2016-06-16 09:56


# Bottle
[Bottle](http://bottlepy.org/docs/dev/index.html) 是一个与 WSGI 标准兼容的 [单文件](https://github.com/defnull/bottle/blob/master/bottle.py) Web 框架，它除了 [标准库 (stdlib)](https://docs.python.org/3/library/) ，没有其它的任何外部依赖。

<a href="http://bottlepy.org/docs/dev/index.html" style="border: none;"><img src="/img/bottle-logo.png" width="100%" alt="Official Bottle logo." class="technical-diagram"></a>


## 我应该使用 Bottle 进行开发吗？
Bottle 特别适合于以下几种情况：

1. 进行原型概念开发
1. 学习 Web 框架是如何构建的
1. 创建和运行简单的个人网络应用

#### 原型开发
相比于庞大复杂的 [Django](/django.html), 使用 Bottle 对简单的概念进行原型开发更加容易，因为创建一个 Django 项目需要相当数量的样板代码。 项目中的 Django App 都是以 [模型-视图-模板](https://docs.djangoproject.com/en/1.9/faq/general/#django-appears-to-be-a-mvc-framework-but-you-call-the-controller-the-view-and-the-view-the-template-how-come-you-don-t-use-the-standard-names) 方式组织的，这样虽然易于项目维护，但是对于一个初始项目来说，会显得有点笨拙，因为你现在只是想尝试实现一些灵感，并不想考虑应用系统的长期代码结构。

#### 学习框架知识
Bottle 包含在[一个单独的大文件中](https://github.com/bottlepy/bottle/blob/master/bottle.py)，名叫 `bottle.py`，因此能够从中学习 [WSGI](/wsgi-servers.html) Web 框架是如何运行的。关于你的 Web 应用代码与 Bottle 框架是如何关联的等等所有你需要了解的东西都在那个单独的源代码文件中。

#### 个人项目
个人项目的部署只需要 Bottle 这个唯一的依赖文件。
如果你之前从没进行过 [Python Web 应用部署工作](/deployment.html)，部署涉及到的大量概念和步骤会让你望而却步的。通过将 `bottle.py` 和你的应用源代码一起打包，可以让你省掉一些步骤，从而使你的 Web 应用更易上线运行。

<div class="well see-also">Bottle 是对 <a href="/web-frameworks.html">Web 框架</a> 概念的一种实现。在 <a href="/web-development.html">Web 开发</a> 那一章你可以了解框架的各部分组件是如何协同工作的，或者到  <a href="/table-of-contents.html">总目录</a> 页去查看其它所有主题。</div>


## Bottle 资源
* [Ubuntu 16.04 LTS 开发：配置 Python 3、 Bottle 和 Gunicorn](/blog/python-3-bottle-gunicorn-ubuntu-1604-xenial-xerus.html) 这篇简洁的教程讲解了如何在默认安装的 Ubuntu 16.04 上进行配置，以用于 Bottle 开发，并使用 [Green Unicorn](/green-unicorn-gunicorn.html) 作为 [WSGI 服务器](/wsgi-servers.html)。

* Digital Ocean 提供了大量的 [Bottle 入门文章](https://www.digitalocean.com/community/articles/how-to-use-the-bottle-micro-framework-to-develop-python-web-apps)。

* [官方的 Bottle 教程](http://bottlepy.org/docs/dev/tutorial.html) 为该框架的基本概念和功能特性提供了详细的说明。

* [使用 Bottle 进行开发 ](https://realpython.com/blog/python/developing-with-bottle-part-1/) 详述了如何用 Bottle 创建一个简单的应用。

* 这份教程对如何 [着手进行 Bottle 开发](http://www.giantflyingsaucer.com/blog/?p=3598) 进行了演示。

* 这里是一份简短的代码片段，它演示了 [如何使用 Bottle 和 MongoDB 创建一个 RESTful API 应用](http://myadventuresincoding.wordpress.com/2011/01/02/creating-a-rest-api-in-python-using-bottle-and-mongodb/)。

* 这份 [教程](http://gotofritz.net/blog/weekly-challenge/restful-python-api-bottle/) 也是演示如何使用 Bottle 创建一个 RESTful Web API 应用的。

* [砰！一个“短栈” Web 框架](http://reachtim.com/articles/BAM-Short-Stack.html) 演示了如何使用 Bottle、 Apache 和 MongoDB 创建一个网络应用。

* [Bottle, 不用 Django 进行全栈开发](http://www.avelino.xxx/2014/12/bottle-full-stack-without-django) 演示了如何在 Bottle 中连接 SQLAlchemy， 并使用该框架创建一个示例应用。

* [在生产环境中使用 bottle.py](http://nongraphical.com/2012/08/using-bottle-py-in-production/) 上有几条很好的建议，是关于 Bottle 应用在生产环境下的部署问题的。

* [Jinja2 模板与 Bottle](http://reliablybroken.com/b/2013/12/jinja2-templates-and-bottle/) 展示了如何使用 Jinja 来替代内置的模板引擎对 Bottle 页面进行渲染呈现。

* [如何使用 Bottle 和 Jinja2 来创建一个能在 Google App Engine 上运行的应用](http://joemartaganna.com/jtblog/how-to-build-a-web-app-using-bottle-with-jinja2-in-google-app-engine.html) 为如何在 Google App Engine [platform-as-a-service](/platform-as-a-service.html) 上使用 Bottle 提供了指导。


## 开源 Bottle 示例项目
* [Pattle](https://github.com/thekad/pasttle) 是 pastebin 的克隆版本， 它是用 Bottle 创建的。

* [Decanter](http://gengo.github.io/decanter/) 是一个对 Bottle 项目进行组织管理的库。

* [compare-python-web-frameworks](https://github.com/makaimc/compare-python-web-frameworks) 上提供了一个示例应用，并以 Bottle 作为其中的一种实现方式。


## Bottle 框架学习清单
1. [下载 Bottle](https://github.com/defnull/bottle/raw/master/bottle.py) 或者使用 pip 在你的本地开发机上通过 ``pip install bottle`` 安装。

1. 练习 [Bottle 教程](http://bottlepy.org/docs/dev/tutorial.html)。

1. 在通读官方的教程及对上面列出的开源示例应用进行研究后，开始编写你自己的 Bottle 应用。

1. 查看 [部署那一章](/deployment.html), 将你的首个 Bottle 应用发布上网上。
