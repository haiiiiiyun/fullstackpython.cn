title: 代码度量
category: page
slug: code-metrics
sortorder: 0805
toc: False
sidebartitle: 代码度量
meta: 借助于分析工具，代码度量可以让开发者深入地了解代码库的质量。快来 Full Stack Python 学习更多关于代码度量的知识吧。
translators: blog.chriscabin.com
updated: 2016-07-07 11:00


# 代码度量
代码度量信息由静态代码分析工具生成，它能用于判定代码的复杂性及非标准做法。

## 代码度量缘何重要？
利用代码度量，开发人员可以找到那些可能需要返工的问题代码区域。此外，一些度量概念，例如“技术债务”，有助于开发者就系统为何会出错等问题与非技术人员进行沟通。

##开源的代码度量项目
* [Radon](http://radon.readthedocs.org/en/latest/index.html)  这个工具用于获取代码行数、圈复杂度、Halstead 指标以及可维护性指数这些原始的代码度量值。

* [Pylint](http://www.pylint.org/) 包含了用于检查代码是否符合 PEP8 风格、设计、例外等检查工具，以及许多其它的源码分析工具。

* [PyFlakes](https://pypi.python.org/pypi/pyflakes) 通过解析源文件来查找其中的错误，并为它们生成相应的报告。

* [Pyntch](http://www.unixuser.org/~euske/python/pyntch/index.html) 是一个试图检测运行时错误的静态代码分析器。但它并不检查代码的风格。


## 托管的代码度量服务
* [Coveralls](https://coveralls.io) 可以通过测试套件获得代码覆盖率，并且结合其它的度量值来帮助开发人员改善代码质量。


## 代码度量相关的资源
* [Python 的静态代码分析器](http://doughellmann.com/2008/03/01/static-code-analizers-for-python.html) 虽然是一篇比较旧的文章，但它讲解了 Python 静态代码分析器是用来做什么这个基础知识。

* 这个 [Stack Overflow 上关于 Python 静态代码分析工具的问题](http://stackoverflow.com/questions/1428872/pylint-pychecker-or-pyflakes) 包含了对 PyLint、 PyChecker 和 PyFlakes 这些工具的对比探讨。

* [Pylint 入门](http://jbisbee.blogspot.ca/2014/04/getting-started-with-pylint.html) 讲述了 Pylint 的设置， .pylintrc 文件的创建以及配置文件所含的内容。

* 这篇文章 [关于社区都用什么 linter 的调查](https://www.reddit.com/r/Python/comments/3oyjva/what_python_linter_do_you_use_poll/) 提供了一些仅仅使用 PyCharm 的代码检测功能的点子以及一些其它的方法。
