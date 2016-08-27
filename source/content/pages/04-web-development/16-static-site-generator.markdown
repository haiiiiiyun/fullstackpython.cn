title: 静态网站生成器
category: page
slug: static-site-generator
sortorder: 0416
toc: False
sidebartitle: 静态网站生成器
meta: 静态网站生成器使用标记语言和模板引擎来生成 HTML 文件。到 Full Stack Python 上学习更多知识。
updated: 2016-07-01 16:45--2016-07-05 23:50


# 静态网站生成器

静态网站生成器结合标记语言（如 Markdown 或 reStructuredText）以及模板引擎，如 [Jinja](http://jinja.pocoo.org/), 来生成 HTML 文件。这些 HTML 文件可以通过 [Web 服务器](/web-servers.html) 或者 [内容分发网络 (CDN)](/static-content.html) 进行部署发布，而无需依赖 [WSGI 服务器](/wsgi-servers.html) 等其它东西。


## 为什么说静态网站生成器很有用？

[静态内容文件](/static-content.html) 如 HTML、CSS 和 JavaScript 文件可以由内容分发网络 (CDN) 来提供服务，以实现高规模及低成本的目标。静态内容网站一旦遇到高并发流量，能很容易地通过 CDN 来提供服务而不会丢失连接。

例如，在[Full Stack Python 网站被推到 Hacker News 首页](https://news.ycombinator.com/item?id=7985692) 的那个周末，由于本网站是通过将 [GitHub Pages](https://pages.github.com/) 作为 CDN 来提供服务的，因此并发连接即便接近 400 个时也没有碰到任何问题，如下图所示，该图是在流量井喷期间截取的 Google Analytics 截图。

<img src="/img/hacker-news-traffic.jpg" width="100%" alt="Example of how static websites scale with a CDN based on Full Stack Python on Hacker News front page traffic." class="technical-diagram">


## 静态网站生成器是如何工作的？

静态网站生成器允许用户通过使用某种标识语言编写模板文件来创建 HTML 文件。然后静态网站生成器结合标记语言和模板文件来生成 HTML 文件。输出的 HTML 文件不需要手工维护，因为当标签或者模板每次被修改后，它都能重新被创建出来。

例如，如下图所示， Pelican 静态网站生成器能将 reStructuredText 文件和 Jinja2 模板文件作为输入，然后将它们组合并输出一组静态 HTML 文件。

<img src="/img/pelican-flow.jpg" width="100%" alt="Example of how static site generators work with a markup language and templates." class="technical-diagram">


## 使用静态网站生成器的缺点是什么？

最大的缺点是： 代码无法在网站生成后执行。你只能使用这些输出文件，因此如果你习惯用传统的 [Web 框架](/web-frameworks.html) 创建 Web 应用的话，你得改变下你的期望。

那些需要数据库来实现的功能，如评论、会话及用户数据，只能通过第三方的服务来提供。例如，如果你想在一个静态网站上添加评论功能，你需要 [嵌入 Disqus 的评论框](https://disqus.com/)，从而只能完全依赖他们提供的功能。

很多的 Web 应用都不能简单地通过静态网站生成器来生成。但是，静态网站生成器可以用来生成网站的部分内容，并通过 Web 服务器来部署，而网站的其它页面可以由 WSGI 服务器来处理。如果处理得当，这种类型的 Web 应用比那些全部页面都由 WSGI 服务器呈现的应用更具扩展潜力。其增加的复杂度对于你的特定应用来说，可能是值得的，也可能并不值得。

## Python 的实现

存在很多用不同的语言实现的静态网站生成器。以下列出的这些主要都是用 Python 编写的。

* [Pelican](http://blog.getpelican.com/) ([源代码](https://github.com/getpelican/pelican)) 是一个常用的 Python 静态网站生成器， [Full Stack Python](https://github.com/mattmakai/fullstackpython.com) 网站就是用它创建的。它的主要模板引擎是 Jinja，并且在默认配置下就支持 Markdown、 reStructuredText 及 AsciiDoc。

* [MkDocs](http://www.mkdocs.org/) ([源代码](https://github.com/mkdocs/mkdocs/)) 使用 YAML 配置文件，并能将 Markdown 文件和一个可选的主题作为输入来创建一个文档网站。它的模板引擎是 Jinja，但是用户通常不必创建自己的模板，除非该特定的网站真得需要，但是如果是这样的话，采用其它的静态网站生成器可能会更加合适。

* [Nikola](https://getnikola.com/) ([源代码](https://github.com/getnikola/nikola)) 支持 reStructuredText、 Markdown 及 Jupyter (IPython) Notebooks 等文件，它能将这些文件与 Mako 或 Jinja2 模板结合来创建静态网站。它同时兼容 Python 2.7 和 3.3。对 Python 2.7 的支持会一直到 2016 年年初，而 Python 3.3 会继续得到支持。

* [Acrylamid](http://posativ.org/acrylamid/) ([源代码](https://github.com/posativ/acrylamid)) 使用增量方式来生成静态网站，因此相比每次当输入文件被修改后都重新生成所有页面的生成方式，它处理的更快。

* [Hyde](http://hyde.github.io/) ([源代码](https://github.com/hyde/hyde)) 最初是作为 Ruby 流行的 [静态网站生成器 Jekyll](http://jekyllrb.com/) 的 Python 版本而开始开发的。今天的这个项目已经不是原来的 "Jekyll 克隆版" 了。Hyde 支持 Jinja 及其它的模板语言，它更加注重通过标记文件中的元数据来指示生成器如何产生输出文件。 通过浏览这些 [使用了 Hyde 的网站](https://github.com/hyde/hyde/wiki/Hyde-Powered) 页面，可以看看用 Hyde 创建的实际网站示例。

* [Grow SDK](http://growsdk.org/) ([源代码](http://growsdk.org/)) 使用工程（通过叫 pods ），工程中包含一个特殊文件和目录结构，来生成网站。该项目当前停留在 "试验“ 阶段。

* [Lektor](https://www.getlektor.com/) ([源代码](https://github.com/lektor/lektor)) 是一个 Python 的静态内容管理系统，它可以部署到任何的 Web 服务器上。它的 [模板引擎](/template-engines.html) 采用 [Jinja2](/jinja2.html)。

* [Complexity](http://complexity.readthedocs.org/en/latest/) ([源代码](https://github.com/audreyr/complexity)) 是一款为喜欢使用 HTML 的人准备的网站生成器。它使用 HTML 来创建模板，同时又从 Jinja 那继承了一些功能。它同时兼容 Python 2.6+、 3.3+ 和 PyPy。

* Cactus ([源代码](https://github.com/koenbok/Cactus/)) 使用 Django 模板引擎，该引擎在创建时就考虑了前端设计人员的需求。它同时兼容 Python 2.x 和 3.x。


### 开源 Python 静态网站生成器示例
* 本网站 [有自己的 GitHub 库并且是完全开源的](https://github.com/mattmakai/fullstackpython.com)，基于 MIT 许可发布。快来 Fork 吧！ 

* [Django REST 框架](https://github.com/tomchristie/django-rest-framework/tree/master/docs) 使用 MkDocs 来创建它的文档网站。一定要看下 [mkdocs.yml 文件](https://github.com/tomchristie/django-rest-framework/blob/master/mkdocs.yml)，通过它可以了解该项目的这份如此丰富、文风优美的文档是如何组织的。

* [实践 Web 开发](https://www.vlent.nl/) 使用 Acrylamid 创建它的网站。它的代码发布在 [GitHub 上并且是开源的](https://github.com/markvl/www.vlent.nl)。

* [Linux 开放管理日 (Loadsys)](http://loadays.org/) [这个网站是开源的，并且可以方便获取](https://github.com/loadays/pelican-site)。

* [Pythonic Perambulations](http://jakevdp.github.io/) 这个博客的主题风格虽然很普通，但是它 [也是开源的，并且也发布在 GitHub 上](https://github.com/jakevdp/PythonicPerambulations)。


### 静态网站生成器资源
* [使用 Pelican 创建一个静态博客的漫漫之路](http://www.notionsandnotes.org/tech/web-development/pelican-static-blog-setup.html) 这篇精彩的文章真正对相关知识进行了深入细致的讲解。

* [Staticgen](https://www.staticgen.com/) 网站上列出了所有编程语言的静态网站生成器，并依据不同的属性进行了排序，如 GitHub 上的 stars 数， fork 数 和 issue 数等。

* [使用 S3 和 Cloudflare 部署静态网站](https://wsvincent.com/static-site-hosting-with-s3-and-cloudflare/) 讲解了如何设置 S3 存储段，并在前端配置 Cloudflare 作为 CDN，以通过 HTTPS 来提供内容服务。你应该可以使用 Amazon Cloudfront 来实现大致相同的设置，但是作为一个 Cloudflare 用户，我还是喜欢它们的这种静态网站配置服务。

* [Pelican 和 GitHub pages 入门简介](http://www.mattmakai.com/introduction-to-pelican.html) 是我写的一篇教程，详解了如何运行 Full Stack Python 的源代码，该网站使用 Pelican 来创建。

* 标题起得是有点大，但是这篇文章就 [为什么说静态网站生成器以后会大有可为](http://www.smashingmagazine.com/2015/11/modern-static-website-generators-next-big-thing/) 这个论点还是论述的非常详实。 我想说的是：静态网站生成器已经流行很长一段时间了。

* 静态网站生成器可以用于创建从小项目和大型站点的各种网站。这篇由 [WeWork 发布的文章：为什么他们使用静态网站生成器](http://engineering.wework.com/engineering/2015/12/08/why-wework-com-uses-a-static-generator-and-why-you-should-too/) 从一个大公司的角度对其进行了讲解。

* [Pelican 和 GitHub pages 入门简介](http://www.mattmakai.com/introduction-to-pelican.html) 是我写的一篇教程，讲解如何使用 Full Stack Python 的源代码来创建和部署你的首个静态网站。

* [放弃 Wordpress 并成为一个时髦的人](http://razius.com/articles/ditching-wordpress-and-becoming-one-of-the-cool-kids/) 详述了一个开发者从 Wordpress 转移到使用 Pelican 和 reStructuredText 来创建他的个人博客的经历。
