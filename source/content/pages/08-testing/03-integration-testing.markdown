title: 集成测试
category: page
slug: integration-testing
sortorder: 0803
toc: False
sidebartitle: 集成测试
meta: 集成测试通过一次性地对系统多个单元进行测试来检测系统它们的正确性。快来 Full Stack Python 学习更多的知识吧。
translators: blog.chriscabin.com
updated: 2016-07-06 15:00


# 集成测试
集成测试通过一次性地检测程序的两个或者更多个单元， 
包括单元之间的接口，来判断它们能否按照预期工作。当代码库中不同的单元相互调用，并且在它们之间传递数据时，利用这种形式的 [测试](/testing.html) 就可以发现单元接口中存在的漏洞。


## 集成测试和单元之间测试有何区别？
与 [单元测试](/unit-testing.html) 用于在独立的函数中寻找 bug  不同，集成测试则是将系统作为一个整体进行测试的。 应当把这个两种形式的测试结合起来，而不仅仅只用一种测试而忽略了另一种。当系统被彻底地进行了单元测试后， 那将使得集成测试变得更加容易，因为很多存在于独立组件中的 bug 都在单元测试中得到解决了。

纵使代码库逐渐变大后，开发者也能借助单元测试或集成测试快速地发现代码中的重大变更。很多时候，这些重大的代码变更都是无意识的，并且不为人所知，直到开发后期才被发现；甚至还可能是最终的软件用户发现这个问题。自动化的单元和集成测试将会大大增加在开发期间就可以尽可能快地找出软件 bug 的可能性，以便快速定位这些 bug 。


### 集成测试相关的资源
* [使用上下文管理器进行集成测试](http://eigenhombre.com/2013/04/13/integration-testing-in-python-with-context-managers/) 给出了一个需要集成测试的系统的例子， 并且展示了如何使用上下文管理器来定位发生的问题。 还有一些其他测试系列的文章，包括 
  [关于集成测试的思考](http://eigenhombre.com/2013/04/18/thoughts-on-integration-testing/) 以及 [集成测试中的线程和进程对比](http://eigenhombre.com/2013/04/19/processes-vs-threads-for-testing/) 。

* Pytest 网站中有一页是讲解 [集成测试良好实践](https://pytest.org/latest/goodpractices.html) 的，所以当你测试自己的应用时，不妨去关注一下。

* [集成测试，或者怎样睡个安稳觉](http://enterprisecraftsmanship.com/2015/07/13/integration-testing-or-how-to-sleep-well-at-nights/) 讲解了什么是集成测
试并且给出了一个集成测试的示例。虽说示例是使用 Java 编写的，但仍然和你在学习集成测试知识有关。
