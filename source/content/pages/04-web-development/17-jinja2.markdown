title: Jinja2 
category: page 
slug: jinja2 
sortorder: 0417
toc: False
sidebartitle: Jinja2
meta: Jinja2 是一个用 Python 编写的模板引擎，它用于输出 HTML 和 XML 等的格式文件。
updated: 2016-07-06 11:30
authors: haiiiiiyun.github.io

# Jinja2

[Jinja2](http://jinja.pocoo.org/docs/dev/) 是一个 Python [模板引擎](/template-engines.html)，用于创建 HTML、XML 等其它标记格式文件，这些文件能通过 HTTP 响应返回给用户。

## 为什么说 Jinja2 很有用？

Jinja2 有用的原因是：它具有一致的模板标签语法，并且该项目完全是作为 [一个独立的开源项目](https://github.com/mitsuhiko/jinja2) 存在的，因此它能用于其它的代码库中。

<div class="well see-also">Jinja2 是对 <a href="/template-engines.html">模板引擎</a> 概念的一种实现。 到 <a href="/web-development.html">Web 开发</a> 那一章去学习更多相关知识，或者到 <a href="/table-of-contents.html">总目录</a> 页去查看其它所有主题。</div>

对于一个模板引擎的代码功能来说，一个极端是允许将任意的代码嵌入到模板中，另一个极端是允许一个开发者在模板中编写任何她想要的功能。Jinja2 的实现经过了大量的考虑 ，并在这两者之前取得了一个很好的平衡。

## Jinja2 的起源和发展
Jinja2 的第一个有记录的公开发行版是 [2008 的 2.0rc1](http://jinja.pocoo.org/docs/dev/changelog/#version-2-0rc1)。自那之后，该引擎进行了大量的更新，且一直处于活跃开发状态。

Jinja2 引擎当然不是最好的模板引擎。实际上，Jinja2 语法是受到 Django 内置模板引擎启发的， Django 的相关引擎在好几年前就已发布了。之前就已经有很多的模板系统了，例如 [JavaServer 页面 (JSPs)](https://en.wikipedia.org/wiki/JavaServer_Pages)，它就比 Jinja2 将近早了十年。Jinja2 的创建吸收了其它模板引擎的经验，而今它在 Python 社区中有着广泛应用。


## 哪些项目使用了 Jinja2？
Jinja2 是一个在 [Web 框架](/web-frameworks.html) 中经常使用的模板引擎，像 [Flask](/flask.html)、[Bottle](/bottle.html)、 [Morepath](/morepath.html) 以及随着 1.8 版的更新，现在的 [Django](/django.html) 也可选用该引擎了。 Jinja2 也被 [配置管理](/configuration-management.html) 工具 Ansible 、[静态网站生成器](/static-site-generator.html) Pelican 等其它许多类似工具用作模板语言。

其目标是：当开发人员已经通过某个项目学会了 Jinja2，那么在另一个需要模板功能的项目中就可以使用完全相同的语法和样式。复用降低了学习曲线并使得开源项目作者免于重造一种新的模板样式。

### Jinja2 相关资源
* 《Real Python》 上有篇很好的 [Jinja2 入门资料](https://realpython.com/blog/python/primer-on-jinja-templating/)，它通过大量的示例代码向我们讲解了如何使用模板引擎。

* [《Flask mega 教程》的第二部分](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-ii-templates) 都是讲述 Jinja2 模板的。讲述了控制流、模板继承以及该引擎的其它标准特性。

* [在 Django 1.8 的 Admin 中升级使用 Jinja2 模板](http://jonathanchu.is/posts/upgrading-jinja2-templates-django-18-with-admin/) 讲解了如何修复一个当 Django 1.8 将 Jinja2 作为模板引擎时会出现的一个问题。

* 官方的 [Jinja2 模板设计师文档](http://jinja.pocoo.org/docs/dev/templates/) 毫无疑问是相当有用的，它即可以作为参考使用，也可以进行通读，从而学习如何正确地使用模板标签。

* 如果你想在 [Web 框架](/web-frameworks.html) 或者其它现有工具之外使用 Jinja2 的话，这里有一份 [非常实用的快速加载函数代码段](http://www.pydanny.com/jinja2-quick-load-function.html)，它能使该模板引擎更加容易用于脚本和 REPL 环境中。

* 当 Jinja2 和 LaTeX 一起使用时，一些 Jinja2 段会与 LaTeX 命令冲突。查看这篇文章 [LaTeX 模板通过 Python 和 Jinja2 来生成 PDF](http://eosrei.net/articles/2015/11/latex-templates-python-and-jinja2-generate-pdfs) 来了解如何解决这些问题。

* 如果你经常使用 Jinja2 的话，你一定会有想在模板文件中转义大段 Jinja2 格式文本的情况。如果需要这样做的话，可以看看 ["raw" 模板标签](http://stackoverflow.com/questions/25359898/escape-jinja2-syntax-in-a-jinja2-template)。
