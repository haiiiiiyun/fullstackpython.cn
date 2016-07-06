title: 集成测试
category: page
slug: integration-testing
sortorder: 0803
toc: False
sidebartitle: 集成测试
meta: 集成测试通过一次性地对系统多个单元进行测试来检测系统的正确性。快来 Full Stack Python 学习更多的知识吧。
translators: blog.chriscabin.com
updated: 2016-07-06 15:00


# 集成测试
集成测试通过一次性地检测程序的两个或者更多个单元，包括单元之间的接口交互，来判断它们能否按照预期工作。当代码库中不同的单元间相互调用并且互传数据时，利用这种类型的 [测试](/testing.html) 就可以发现接口中存在的漏洞。


## 集成测试和单元之间测试有何区别？
与 [单元测试](/unit-testing.html) 用于在单独的函数中寻找 bug 不同，集成测试则是将系统作为一个整体进行测试的。 这两种类型的测试应当结合起来使用，而不能只用一种测试而忽略了另一种。当系统进行了全面地单元测试后，集成测试将变得更加容易，因为很多存在于独立组件中的 bug 都已被找到被修复了。

随着代码库逐渐变大，单元测试和集成测试能使开发人员能快速地识别出代码中的破坏性变更。很多时候，这些破坏性的变更都是意料之外的，并且会一起存在到开发后期才会被发现，甚至还可能是最终的用户在使用软件时才发现这个问题。自动化的单元和集成测试将会大大提高在开发期间尽快找出 bug 的可能性，从而使它们能立即被处理掉。

### 集成测试相关的资源
* [使用上下文管理器进行集成测试](http://eigenhombre.com/2013/04/13/integration-testing-in-python-with-context-managers/) 给出了一个需要进行集成测试的示例系统，并且展示了如何使用上下文管理器来定位发生的问题。该有关测试的系列文章中，还有几篇很有用的文章，包括 [关于集成测试的思考](http://eigenhombre.com/2013/04/18/thoughts-on-integration-testing/) 以及 [集成测试中的线程和进程对比](http://eigenhombre.com/2013/04/19/processes-vs-threads-for-testing/)等。

* Pytest 网站中有一页是讲解 [集成测试良好实践](https://pytest.org/latest/goodpractices.html) 的，当你对你的应用进行测试时，不妨参考下。

* [集成测试，或者怎样睡个安稳觉](http://enterprisecraftsmanship.com/2015/07/13/integration-testing-or-how-to-sleep-well-at-nights/) 讲解了什么是集成测试并且给出了一个集成测试的示例。虽说示例是使用 Java 编写的，但仍然和你学习集成测试知识有关。
