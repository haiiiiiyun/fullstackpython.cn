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
通过使用静态代码分析工具来生成代码度量信息，从而判断代码的质量和一些其他的非标准实践。


## 代码度量缘何重要？
利用代码度量，开发人员可以找到那些可能需要返工的问题代码区域。此外，一些度量概念，例如“技术债务”，可以帮助开发者和非技术人员探讨为什么一个系统会发生问题。 

##开源的代码度量项目
* [Radon](http://radon.readthedocs.org/en/latest/index.html)  是一个这样的工具，它用于获取代码行数、圈复杂度、霍尔斯特德指标以及可维护性指数这些原始的代码度量值。

* [Pylint](http://www.pylint.org/) 包含了一个用于检查代码是否符合 PEP8 风格的设计、异常的检查工具， 以及许多其它的源码分析工具。

* [PyFlakes](https://pypi.python.org/pypi/pyflakes) 用于检查源文件中的错误，并为它们生成相应的报告。

* [Pyntch](http://www.unixuser.org/~euske/python/pyntch/index.html) 是一个用于尝试检查代码运行时错误的静态代码分析器。但它并不检查代码的风格。


## 托管的代码度量服务
* [Coveralls](https://coveralls.io) 可以通过测试套件获得代码覆盖率并且会报告一些其他的代码度量值，从而帮助开发者们改善他们的代码质量。


## 代码度量相关的资源
* [用于 Python 的静态代码分析器](http://doughellmann.com/2008/03/01/static-code-analizers-for-python.html)
  虽然是一篇比较旧的文章，但它讲解了 Python 静态代码分析器可以做什么的基础知识。

* 这个 [Stack Overflow 上关于 Python 静态代码分析工具的问题](http://stackoverflow.com/questions/1428872/pylint-pychecker-or-pyflakes)
  包含了对 PyLint, PyChecker 和 PyFlakes 这些工具的对比和探讨。

* [入门 Pylint](http://jbisbee.blogspot.ca/2014/04/getting-started-with-pylint.html) 告诉你如何设置 Pylint，如何生成 .pylintrc 文件，并且说明了配置文件里面都是什么。

* 这篇文章 [关于社区都用什么 linter 的调查](https://www.reddit.com/r/Python/comments/3oyjva/what_python_linter_do_you_use_poll/) 提供了一些仅仅使用 PyCharm 的 linting 特性的输入方法以及一些其他的技巧。

