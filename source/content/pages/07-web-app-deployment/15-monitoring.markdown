title: 监控
category: page
slug: monitoring
sortorder: 0715
toc: False
sidebartitle: 监控
meta: 监控工具可以捕获来自应用程序执行的数据并显示出来。快来 Full Stack Python 学习更多有关监控的知识吧。
translators: blog.chriscabin.com
updated: 2016-07-24 20:00


# 监控
监控工具用于收集、分析并展现来自 web 应用执行时的信息。每个应用程序在所有等级的 web 堆栈都会发生问题。
监控工具为开发者和运维团队提供了透明度，使他们能（及时）响应并修复问题。

## 监控为何是必要的？
收集并分析你的生产环境数据是非常重要的，它能帮助积极地解决 web 应用的稳定性、性能和错误等问题。

## 监控与日志的区别
监控和日志的目的是非常类似的，它们能够帮助诊断应用程序的问题并为调试过程提供帮助。
关于它们的区别的一种看法是，日志是在特定的事件发生时产生，而监控则在后台被动地收集数据。

例如，当一个错误发生时，代码中的异常处理函数会将特定的事件通过日志输出。与此同时，监控代理会测量代码并收集数据，这些数据不仅含有异常日志，而且还有函数的运行性能。

日志和监控的这点区别是模糊的，这也并不是区分它们的唯一一种方式。事实上，它们对于维护一个生产环境的 web 应用都是非常有帮助的。

## 监控层
操作系统和 web 堆栈网络级中有好几种重要的资源需要监控。

1. CPU 利用率
2. Memory 利用率
3. 永久性存储器使用占比
4. 网络带宽和延迟

应用级的监控包含多个方面。每个方面对应的时间量和资源量都是不同的，这些取决于应用程序是否有大量的读操作、大量的写操作或者是流量快速波动等特性。

1. 应用程序警告和错误（HTTP 500 错误）
2. 应用程序代码性能
3. 模板渲染时间
4. 应用程序的浏览器渲染时间
5. 数据库查询性能


## 开源监控项目
* [statsd](https://github.com/etsy/statsd/) 是一个 node.js 的网络后台服务，它能够监听测量数据并收集它们，用于传送到其它服务中，如 Graphite。

* [Graphite](https://graphite.readthedocs.org/en/latest/overview.html) 存储基于时间序列的数据并将它们在一个 Django web 应用的图表中显示出来。

* [Bucky](http://github.hubspot.com/bucky/) 测量 web 应用在终端用户浏览器中的运行性能，并把测量数据发送回服务器收集起来。

* [Sensu](http://sensuapp.org/) 是一款使用 Ruby 编写的开源监控框架，但它兼容其它任何语言编写的 web 应用。

* [Graph Explorer](http://vimeo.github.io/graph-explorer/) ，由 Vimeo 编写，它是基于 Graphite 的操作面板，含有一些新增的特性并且设计巧妙。

* [PacketBeat](http://packetbeat.com/) 用于嗅探协议包。后来 Elasticsearch 允许开发者们使用 Kibana 用户界面搜索收集的数据并呈现出 web 应用内部正在发生什么。

* [Munin](http://munin-monitoring.org/) 是一个基于插件的监控系统客户端，它用于将监控数据发送到用于分析并可视化的 Munin 节点。注意这个项目是用 Perl 完成的，所以收集数据的节点上必须要安装 Perl 5。

## 托管的监控服务
* [New Relic](http://newrelic.com/)，用于监控应用程序和数据库，同时它含有用于收集并分析你的堆栈工具的其它数据的插件。

* [CopperEgg](http://copperegg.com/) 是运行在服务器和基础设施上的更低层的监控服务。它在 DevOps 商店非常流行，他们正在改变生产环境并且希望能够立即获得这些修改的反馈信息。

* [Status.io](http://status.io/) 专注于 web 应用的启动时间和响应指标透明度。

* [StatusPage.io](https://www.statuspage.io/) （没错，Status 和 StatusPage.io 都有）提供了简单设置状态页以监控程序启动时间的功能。

* [PagerDuty](http://www.pagerduty.com/) 在应用程序出现稳定性、性能或启动时间等问题发生时会给特定的人员或小组发出警告。

* [App Enlight](https://appenlight.com/) 提供了性能、异常和错误监控功能，并且目前是专门针对 Python web 应用的。

* [Opbeat](https://opbeat.com) 为 Django 构建的。Opbeat 把性能指标、版本跟踪和错误日志集成到单个简易的服务中了。


## 监控相关资源
* [监控的好处](http://www.paperplanes.de/2011/1/5/the_virtues_of_monitoring.html)。

* [使用 collectd, Graphite, 和 Docker 轻易地实现监控](http://blog.docker.io/2013/07/effortless-monitoring-with-collectd-graphite-and-docker/)。

* [StatsD/Graphite 监控实践指南](http://matt.aimonetti.net/posts/2013/06/26/practical-guide-to-graphite-monitoring/) 
  是一篇讲解监控基础设施并含有示例代码的详细的教程。

* Bit.ly 说明了 
  “[10 个他们忘记监控的东西](http://word.bitly.com/post/74839060954/ten-things-to-monitor)”
  ，除了标准的测量，如磁盘、内存使用率之外。

* [4 款 Linux 服务器监控工具](http://aarvik.dk/four-linux-server-monitoring-and-management-tools/)。

* [如何设计有用的监控和图形化工具](https://blog.serverdensity.com/how-to-design-useful-monitoring-graphs-and-visualizations/)

* [测量与监控的 5 年](https://speakerdeck.com/auxesis/5-years-of-metrics-and-monitoring)
  是一篇非常棒的报告，它强调了为了方便人类理解测量的可视化是一个困难的问题。线条图通常并非是最好的方案，而且它们已经被过度利用了。

* Collector Highlight 系列有一篇文章是关于 [StatsD](http://blog.librato.com/posts/statsd) 的，说明了 StatsD 如何安装以及它是怎样工作的。

* 这篇文章 [监控工具调查](http://kartar.net/2014/11/monitoring-survey---tools/)
  有一些开发者和运维人员在他们的环境中所使用的工具的相关数据和图表。

* Ryan Frantz 写了一篇不错的文章
  [解决监控问题](http://ryanfrantz.com/posts/solving-monitoring/)
 ，他给出了新的基于当前复杂系统的监控的定义，并且说明了实践该如何继续演进。


## 监控学习清单
1. 回顾“软件即服务”和以上列出的开源监控工具。第三方服务为你提供了更加简易的设置过程以及数据托管服务。开源项目则会给你更多的控制权，但是你需要拥有用于监控的额外就绪的服务器。

1. 我推荐的方案是安装试用版 [New Relic](http://newrelic.com/) 来学习它是如何与你的应用一同工作的。它能让你领略到应用程序级别的监控工具的能力。

1. 当你的应用扩展时，就去看看如何设置一款开源监控项目，例如带有 Graphite 的 StatsD。集成这两个项目将能为你收集和用于可视化的系统测量数据提供更细粒度的控制。

