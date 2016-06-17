title: Morepath
category: page
slug: morepath
sortorder: 0407
toc: False
sidebartitle: Morepath
meta: Morepath 是一个 Python Web 框架，它使用模型驱动的设计方法。 在 Full Stack Python 上了解更多 Morepath 的知识。
authors: haiiiiiyun.github.io
updated: 2016-06-17 09:21

# Morepath
[Morepath](http://morepath.readthedocs.org/en/latest/) 是一个 Web 微框架，它使用模型驱动的方式来创建 Web 应用和 Web API。

Morepath 的框架理念是： 数据模型应该驱动 Web 框架的应用开发过程。该框架默认将 URL 直接路由到模型代码中，而不像 Django 等框架还需要开发者显式指定 URL 路由。


## 为何说 Morepath 是一个很有趣的 Web 框架？
简单的 [CRUD 型 Web 应用 和 API 应用](http://en.wikipedia.org/wiki/Create,_read,_update_and_delete) 的创建过程会比较枯燥乏味，因为这种应用都是与数据模型直接打交道的，而模型与视图间的逻辑关联很少。你可以从 Morepath 作者那里了解更多有关该框架 [与其它 Web 框架的对比情况](http://morepath.readthedocs.org/en/latest/compared.html)。

随着前端 JavaScript 框架的出现，许多 Python Web 框架开始被用来创建 [RESTful API 应用](/application-programming-interfaces.html)，这些应用只返回 JSON，而不是通过模板系统来呈现 HTML。 Morepath 在设计之初就考虑了 RESTful API 模式方法，并且抛弃了模板驱动用户界面这样的假设。


### Morepath 资源
* [On the Morepath](http://blog.startifact.com/posts/on-the-morepath.html) 是 Startifact 的一篇博客文章，详述他们是如何使用 Morepath 的及该框架的一些特性。

* [和 Morepath 度过的某个夏天](http://blog.stacktrace.ch/post/132538261985) 描述了文章作者使用 Morepath 的一些经验，比如他是如何基于 Morepath 的核心功能来创建一个新框架的。由于他创建的这个应用，他最后成为了 Morepath 项目的一个核心贡献者。

* [使用 Morepath 和 Jinja2 创建一个更好的批处理界面](http://blog.startifact.com/posts/morepath-batching-example.html) 是一篇关于如何使用该框架构建一个简单的 Web 应用的介绍性文章。应用的代码也是 [开源的，发布在 GitHub上](https://github.com/morepath/morepath_batching)。

* Morepath 的作者在 EuroPython 2014 上 [就该新框架的创作动机和架构作了一次很赞的演讲](https://www.youtube.com/watch?v=gyDKMAWPyuY)。
