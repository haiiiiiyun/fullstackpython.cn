title: 单元测试
category: page
slug: unit-testing
sortorder: 0802
toc: False
sidebartitle: 单元测试
meta: 单元测试用于测试从程序中隔离出来的单个函数。快来 Full Stack Python 学习更多关于单元测试的知识吧。
translators: blog.chriscabin.com
updated: 2016-07-05 19:00


# 单元测试
单元测试是一种用于判断从更大的代码库分离出来的单个函数正确性的方法。 单元测试的思想是，如果一个应用程序中所有分离出来的原子单元都能按照预期工作， 那么当把它们集成到一起后，能按照预期工作将会更加容易。


## 单元测试缘何重要？
单元测试只是一种 [测试](/testing.html) 形式，它会和其他测试方法配合在一起，用于查找正在开发的软件中存在的 bug。当把多个函数和类放在一块后，通常来说，如果多个 bug 同时出现的话，将很难定位问题的根源。单元测试能帮助消除尽可能多的独立 bug，从而当一个程序作为一个整体运行时，其各组成部分将越有可能正确运行。那么，一旦出现了问题， 它们通常都可以被追溯为：是因不同的组成部分未能正确衔接而产生的非预期结果。


## 单元测试工具
Python 中有许多用于创建测试的工具。有一些测试工具，例如 pytest，是用来替代内置的 unittest 框架的。 其他的一些测试工具，如 nose 等都是用于简化测试的创建工作的扩展程序。需要注意的是，通过编写测试案例来对代码中的多个部分同时进行测试，这些工具也有许多可被用于 [集成测试](/integration-testing.html)。

* [unittest](https://docs.python.org/3/library/unittest.html) 是专门用于测试 Python 代码的内置标准库工具。

* [pytest](http://pytest.org/latest/) 是一个完整的测试工具，它强调后向兼容性及最少化样板代码量。

* [nose](https://nose.readthedocs.org/en/latest/) 是一个 unittest 的扩展工具，它使得编写和执行测试案列更加简单。

* [Hypothesis](http://hypothesis.readthedocs.io/en/latest/index.html) 是一个单元测试生成工具，它会帮助开发人员创建用于检查代码块边边界条件的测试案例。 学习使用 Hypothesis 的最好途径就是去认真阅读这篇写得非常好的 [快速入门](http://hypothesis.readthedocs.io/en/latest/quickstart.html)。

* [testify](https://github.com/Yelp/Testify/)  是一个旨在替代 unittest+nose 组合的测试框架。 遗憾的是，testify 背后的开发团队正在转向 pytest，所以并不推荐你在新的项目中使用 testify。


### 单元测试相关的资源
* [《深入 Python 3》 中的单元测试相关章节](http://www.diveintopython3.net/unit-testing.html) 中有一个完整的代码示例，并且详细讲解了如何使用 [unittest](https://docs.python.org/3/library/unittest.html) 模块来创建单元测试。

* [使用 Python 的 Flask 和 Nose 为你的 Twilio 应用进行单元测试](https://www.twilio.com/blog/2014/03/unit-testing-your-twilio-app-using-pythons-flask-and-nose.html) 是一篇详细的教程，它讲解了如何使用 nose 来确保一个 Flask 应用能够正常运行。

* [理解单元测试](https://jeffknupp.com/blog/2013/12/09/improve-your-python-understanding-unit-testing/) 一文说明了测试为何重要，并且展示了如何在你的应用中有效地进行测试。

* [使用 Python 做单元测试](http://www.drdobbs.com/testing/unit-testing-with-python/240165163) 从更高的层面来看待测试，并且提供了一些图表用于展示在测试周期中究竟发生了什么。

* Python 的维基站上有一页列出了 [Python 的测试工具及其扩展](https://wiki.python.org/moin/PythonTestingToolsTaxonomy)。

* [高效单元测试](http://blog.fogcreek.com/working-effectively-with-unit-tests-interview-with-jay-fields/) 是一篇针对《高效单元测试》（Working Effectively with Unit Tests）一书作者的采访，他在那儿分享了一些关于这个话题的高见。

* [生成你的测试](http://blog.kevinastone.com/generate-your-tests.html) 一文教你如何编写一个可以配合 `unittest` 框架工作的测试生成器。

* [nose 单元测试框架的延伸介绍](http://ivory.idyll.org/articles/nose-intro.html) 展示了如何利用这个工具来编写基础的测试套件。虽然这篇文章是 2006 年的，但是它仍然适用于今天，你可以从中学习到如何在你的项目中使用 nose。
