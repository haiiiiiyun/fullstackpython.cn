title: 微服务
category: page
slug: microservices
sortorder: 0719
toc: False
sidebartitle: 微服务
meta: 微服务是指一种架构，在该架构中独立的、包含功能的程序通过网络调用进行交流。
translators: blog.chriscabin.com
updated: 2016-07-28 16:50


# 微服务
微服务是一种应用程序架构风格，它让拥有单独功能的自包含程序通过网络和其它程序通信。典型地，这些微服务可以分开部署，因为它们通过一个定义良好的规格说明和有效的后向兼容性使得它们职责分明，从而可以避免突如其来的依赖破坏问题。


## 为何微服务变得如此流行？
微服务遵循长久以来软件架构模式风行的趋势。从前，[CORBA](https://en.wikipedia.org/wiki/Common_Object_Request_Broker_Architecture) 和（多数基于 XML的）面向服务的架构（SOA）成为 [架构象牙塔](http://www.igloocoder.com/2271/ivory-tower-architect) 中的流行词。

然而，微服务更实在，因为它们通常基于 [RESTful API](/application-programming-interfaces.html)，这对于实际的软件开发者而言，要比之前由各种企业软件公司发布的基于复杂的 XML 结构的架构容易得多！此外，成功的应用程序开始时都首先采用一种整体为先的方法，它使用一个单独的、共享的应用代码库和部署。只有在应用程序证明了它的有用性后，才会将它打破成微服务组件，从而让今后的开发和部署更轻松。这种方法叫做“整体为先”或者 “[整体为先](http://martinfowler.com/bliki/MonolithFirst.html)”模式。


### 微服务相关资源
* Martin Fowler 写的
  [微服务](http://martinfowler.com/articles/microservices.html)
  是最佳的深入剖析什么是微服务以及为何将它们当做一种架构模式的文章之一。

* [为什么是微服务？](http://dev.otto.de/2016/03/20/why-microservices/)
  给出了一个很好的微服务架构能够在正确的情形下提供的一些优点，例如，大幅度增加每日部署的次数。

* [关于整体和微服务](http://dev.otto.de/2015/09/30/on-monoliths-and-microservices/)
  给出了一些在软件项目早期使用微服务的建议。

* [用 Python 开发一个 RESTful 微服务](http://www.skybert.net/python/developing-a-restful-micro-service-in-python/)
  是一个讲述了如何使用 Python 和 Flask 替换一个老旧的 Java 项目的故事。

* [微服务：基本实践](http://technologyconversations.com/2015/11/10/microservices-the-essential-practices/)
  首先回顾了一个整体应用程序是什么样的，然后深入讲解了你需要做点什么来支持潜在的微服务。例如，你真的需要将持续集成和部署设置好。这是有关该话题非常好的高级综述，很多开发者在着手将整体架构转换为微服务架构时都没有注意这个话题。

* [使用 Nginx 实现微服务负载均衡](https://hagbarddenstore.se/posts/2016-03-11/using-nginx-to-load-balance-microservices/)
  说明了一个 Nginx 实例如何能够使用来自 etcd 的配置值，当值发生变动时会通过 confd 更新。当安装或去除后端服务时，这个设置对于微服务负载均衡非常有用。

* [微服务是如何改变的以及为何它们很重要](http://thenewstack.io/microservices-changed-matter/)
  是有关该话题的高级综述，它引用了一些来自该行业开发者的话。

* [当前的微服务状况](http://blog.codeship.com/the-state-of-microservices-today/)
  提供了一些一般趋势和广泛数据显示出 2016 年以来微服务的流行度在不断增加。

* [唧唧歪歪微服务](http://jonasboner.com/bla-bla-microservices-bla-bla/) 
  是一个关于微服务的杀手级演讲的文稿，它打破了分布式系统重要的第一原则，包括异步通信、隔离、自动化、单一职责、独立状态以及移动性。这个带有文本的幻灯片深入说明了现实如何变得一团糟，以及如何拥抱分布式系统固有的约束。

