title: 测试
category: page
slug: testing
sortorder: 0801
toc: True
sidebartitle: 8. 测试
meta: 测试代码是Python开发中的一个重要环节。 快来 Full Stack Python 学习更多关于测试的知识吧。
translators: blog.chriscabin.com
updated: 2016-07-05 17:00


# 测试
测试是一种基于特定的输入来判断软件能否正确地运行的方法，并且可以找到需要修复的软件漏洞。


## 测试缘何重要？
因为软件是使用代码库来衡量大小的， 所以，无论是个人还是大型团队，都不可能及时跟进软件所有的变动以及变动之间的交互。事实表明， 一旦软件变得比最初简单原型更加复杂后，自动化测试就是唯一一种可以用来构建健壮的软件的方法了。有很多重要的软件项目失败都是因为缺乏充分并且完善的测试。

对于我们而言，只有软件通过测试后才能够知道它能不能正常工作。
虽然测试工作可以由用户手动点击按钮或者输入来完成，但是更佳的办法是编写专门的测试工具，从而让软件测试能够自动化完成。

现在有许多种形式的测试方法，我们应当将它们一同使用起来。当程序中有一个专门用于测试并且被隔离的函数时，这就叫做
[单元测试](/unit-testing.html)。而当同时测试程序中多个函数时，这就是著名的
[集成测试](/integration-testing.html)。
*用户界面测试* 确保了用户如何与软件交互的正确性 。还有更多大型程序所需要的测试方法，比如 *负载测试*，*数据库测试*以及
*浏览器测试* (针对web应用)。


## 在 Python 中测试
Python 软件开发文化就是非常重视软件测试。 相对于静态类型语言而言，Python 是一种动态类型的语言。 为了确保软件的正确性，测试在 Python 开发中占据了至关重要的地位。


## 测试相关的资源
* [最小的可行测试套件](https://realpython.com/blog/python/the-minimum-viable-test-suite/)
   使用一个 Flask 例子来为我们展示如何进行单元测试和集成测试。

* [好的测试，坏的测试](http://late.am/post/2015/04/20/good-test-bad-test.html)
   说明了“好的”测试和无用的测试之间的差别。 这篇文章打破了一些关于常见测试主题的误区，例如代码覆盖率、断言和mocking测试。

* [Python 测试](http://pythontesting.net/) 是一个（我想你猜到了）专注于 Python 编程语言测试的网站。

* [测试驱动开发案例](http://michaeldehaan.net/post/120522567217/the-case-for-test-driven-development)
  由 Michael DeHaan 发表，它为我们解释了为何自动化测试是构建大规模软件的唯一方法。

* 谷歌有一个[测试博客](http://googletesting.blogspot.com/) ，他们提供了关于大规模软件测试的各方面信息。

* 依然对单元、函数和继承测试的区别感到糊涂吗？ 来看看关于这个问题的回答吧：
  [Stack Overflow上最多的回答](http://stackoverflow.com/questions/4904096/whats-the-difference-between-unit-functional-acceptance-and-integration-test) 。

* [Django 中使用 pytest](http://engineroom.trackmaven.com/blog/using-pytest-with-django/)
    展示了如何获得一个为Django项目运行的基本的[pytest](http://pytest.org/latest/) 测试，并且说明了为何作者更喜欢 pytest，而不是标准的 unittest 测试。

