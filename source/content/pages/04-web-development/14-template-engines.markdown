title: 模板引擎
category: page
slug: template-engines
sortorder: 0414
toc: False
sidebartitle: 模板引擎
meta: 模板引擎提供 HTML、XML 和 PDF 等格式化的内容输出。
updated: 2016-06-22 13:06--2016-06-28

# 模板引擎
模板引擎对模板文件进行处理，模板文件是处于你的 Python 代码和需要输出的格式化内容（如 HTML 和 PDF 等）之间的一种中间格式文件。

## 为什么说模板引擎很重要？
模板引擎允许开发人员创建 HTML 等所需的内容形式，同时，它还提供条件判断和 for 循环等编程构件来对输出进行处理。 模板文件由预定义的标记和待插入内容的模板标签段组成， 这些文件由开发人员创建，然后再由模板引擎处理。

例如，查看当前网页的 HTML 内容的前 10 行源代码：

    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta name="author" content="Matt Makai">
        <meta name="description" content="Template engines provide programmatic output of formatted content such as HTML, XML or PDF.">
        <link rel="shortcut icon" href="//static.fullstackpython.com/fsp-fav.png">

除了 `<meta name="description"...` 这行，它是为各个单独页面提供包含哪些内容的简短描述之外， 上面的各行 HTML 代码对于 Full Stack Python 网站的每个页面来说都是一样的。

[base.html](https://github.com/makaimc/fullstackpython.com/blob/gh-pages/source/theme/templates/base.html) 是用于创建 Full Stack Python 的 Jinja 模板，它使得网站的每个页面都有一致的 HTML 内容结构，同时又能为每个页面动态生成那些在 [静态网站生成器](/static-site-generator.html) 执行时需要修改的内容。下面的代码来自 `base.html` 模板，可以看到 meta 描述是要求子模板来生成的。

    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <meta name="author" content="Matt Makai">
        {% block meta_header %}{% endblock %}
        <link rel="shortcut icon" href="//static.fullstackpython.com/fsp-fav.png">


在一个典型的 [WSGI 应用中](/wsgi-servers.html)，当某个特定 URL 的 HTTP 请求进来后，模板引擎将生成一个 HTML 文件的应答。

## Python 模板引擎
Python 有几个比较流行的模板引擎。从允许执行任意代码，到只准许通过模板标签来执行有限的功能，每个模板引擎都有各自的实现方式。从下图可以看出 Python 的四个主要模板引擎的模板代码功能。

<img src="/img/template-logic-spectrum.png" width="100%" alt="从不含任何逻辑代码到能执行任意代码。" class="technical-diagram" style="border-radius: 5px;">

### Jinja
[Jinja](http://jinja.pocoo.org/), 也叫做 "Jinja2"， 这个广受欢迎的 Python 模板引擎是作为一个独立的开源项目开发的，而不像其它的一些模板引擎那样是某个较大的 Web 框架的一部分。

主要的 Python 开源应用如 [配置管理](/configuration-management.html) 工具 Ansible 和 [SaltStack](https://github.com/saltstack/salt)，以及 [静态网站生成器](/static-site-generator.html) Pelican 等都默认使用 Jinja 来创建输出文件 。

在 [Jinja2](/jinja2.html) 页还有很多很多关于 Jinja 的学习内容。

### Django 模板
Django （如 Django 1.9） 除了支持 Jinja 等其它一些可替代的模板引擎外，它还有 [自己的模板引擎](https://docs.djangoproject.com/en/dev/topics/templates/)。

### Mako
[Mako](http://www.makotemplates.org/) 是 [Pyramid Web 框架](/pyramid.html) 的默认模板引擎，并且因作为许多 [其它 Web 框架](/other-web-frameworks.html)的替代模板引擎而广受支持。


### 模板引擎资源
* [一个只有不到 500 行代码的模板引擎](http://aosabook.org/en/500L/a-template-engine.html) 这篇文章是由 [Ned Batchelder](http://nedbatchelder.com/) 写的，讲解了一个只有 252 行 Python 代码的模板引擎，从中我们学习模板引擎的工作原理。

* [Jinja 模板入门](https://realpython.com/blog/python/primer-on-jinja-templating/) 讲解了如何使用这个无敌模板引擎的主要功能。

* [模板的疑难问题集锦](http://agiliq.com/blog/2015/08/template-fragment-caching-gotchas/) 收集了开发人员和设计师在使用模板时会碰到的各种坑及其解决办法。

* 这个 [模板引擎网站](http://www.simple-is-better.org/template/index.html) 上包含了从什么是模板引擎到一些鲜为人知的 Python 模板引擎等大量信息。
