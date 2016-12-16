title: 任务队列
category: page
slug: task-queues
sortorder: 0711
toc: False
sidebartitle: 任务队列
meta: 任务队列异步处理在 Python web 应用 HTTP 请求-响应循环外的工作。
translators: http://blog.chriscabin.com
updated: 2016-07-20 08:00


# 任务队列
任务队列负责管理后台工作，后台工作必须要在常规的 HTTP 请求-响应周期外执行。

## 任务队列为何是必要的？
任务需要异步执行的原因有两点：第一，它们并非由 HTTP 请求引发；第二，它们都是需要长时间运行并且会严重削弱 HTTP 响应性能的任务。

例如，某个 web 应用可以每 10 分钟去调用 GitHub API 来收集最受关注的 100 个仓库的名称。任务队列可以触发调用 GitHub API 的代码，然后处理返回的结果并存放在一个固定的数据库中，以便后期使用。

另外一个例子就是，在 HTTP 请求-响应周期中，当数据库查询需要花费太长时间时，就可以将查询任务放在后台执行，让它每隔一个固定时间就执行一次查询，并将结果存储在数据库中。当一个 HTTP 请求到来时，如果需要那些结果，只需要进行一次查询即可轻松地获取预先计算好的结果来，而不是再次执行长时间的查询任务。这种预先计算的情景就是一种在任务队列中启用 [缓存](/caching.html) 的例子。

其他需要任务队列的情形包括：

* 将大量独立的数据库插入操作分开在一段时间内插入完成，而不是一次全部插入；

* 在一个固定的时间间隔后收集一次数据值，例如每 15 分钟；

* 安排周期性的工作，例如批处理。


## 任务队列的项目
Celery 是 Python 任务队列事实上的标准。其它任务队列项目的诞生往往是因为 Celery 在一些简单的案例中使用显得过于复杂。我的建议是将精力花费在 Celery 的合理学习曲线上，因为花费这些时间是值得的，它可以帮助理解如何使用这个项目。

* 分布式任务队列 [Celery](http://www.celeryproject.org/) 是最常使用的 Python 库，它用于执行异步任务和周期性任务。 

* [RQ (Redis Queue)](http://python-rq.org/) 是一个简单的 Python 库，用于给工作排队，并在后台处理它们。RQ 由 Redis 提供支持，并且学习门槛较低。
  这篇 [介绍文章](http://nvie.com/posts/introducing-rq/) 包含了 RQ 的设计决策以及如何使用它的相关信息。
  
* [Taskmaster](https://github.com/dcramer/taskmaster) 是一个简单的轻量级分布式任务队列，用于处理大量的一次性执行任务。

* [Huey](http://huey.readthedocs.org/en/latest/) 是一个简单的任务队列，由 Redis 提供后台支持，但除此之外并不依赖于其它库。这个项目是曾经知名的 Invoker，但是后来作者改名为 Huey 了。

* [Huey](http://huey.readthedocs.org/en/latest/) 是一个基于 Redis 的任务队列，旨在提供一个用于执行任务的简单灵活的框架。Huey 支持任务调度、类 crontab 的重复性任务执行、结果存储和在失败时自动重试等功能。

## 托管消息和任务队列服务
第三方任务队列服务旨在解决当扩展部署大量分布式任务队列时产生的问题。

* [Iron.io](http://www.iron.io/) 是一个分布式消息服务平台，它可以和很多类型的任务队列配合工作，例如 Celery。它同样也是可以和其它 IaaS 和 PaaS 环境配合工作的，例如 Amazon Web 服务 和 Heroku。

* [Amazon 简单队列服务 (SQS)](http://aws.amazon.com/sqs/) 是五种 API 的集合，分别用于创建、发送、接收、修改和删除消息。

* [CloudAMQP](http://www.cloudamqp.com/) 是在它的核心管理服务器上安装并配置了 RabbitMQ。如果你正在使用 RabbitMQ，并且不想在你自己的服务器上维护 RabbitMQ 的安装，你可以选择这个服务。

## 使用任务队列的开源案例
* 看看这个开放源码的
  [Flask 应用](https://www.twilio.com/docs/howto/walkthrough/appointment-reminders/python/flask) 
  和 
  [这个 Django 应用](https://www.twilio.com/docs/howto/walkthrough/appointment-reminders/python/django) 
  例子，它们说明了如何使用并部署使用 Redis 作为代理中间件的 Celery 应用，从而使用这些框架发送消息。
  
* [flask-celery 例子](https://github.com/thrisp/flask-celery-example) 是一个简单的 Flask 应用，并且使用 Celery 作为任务队列，Redis 作为代理中间件。


## 任务队列相关资源
* [入门学习使用 Celery 进行调度任务](http://www.caktusgroup.com/blog/2014/06/23/scheduling-tasks-celery/)
  是一个详细讲解了在 Django 中设置并使用 Celery 的教程（虽然在其它框架中使用 Celery 也没有任何问题）。

* [国际空间站上使用 Python 和 Redis 队列（RQ）发送通知](https://www.twilio.com/blog/2015/11/international-space-station-notifications-with-python-redis-queue-and-twilio-copilot.html)
  说明了如何将 RQ 任务队列库和 Flask 组合在一起，从而每当满足一个条件时就发送相应的文本消息通知。就这篇博客来说，国际空间站（ISS）正飞过你所在的地理位置。

* [针对持久、重复性的消息队列的评估](http://www.warski.org/blog/2014/07/evaluating-persistent-replicated-message-queues/)
  是一篇针对 Amazon SQS、MongoDB、RabbitMQ、HornetQ 和 Kafka 设计和性能的详细对比的文章。

* [Queues.io](http://queues.io/) 是一个包含任务队列系统的集合，并且每个系统都有简短的介绍。这些任务队列并非都和 Python 兼容，但是那些可以在 Python 中工作的任务队列都带有 "Python" 关键字。

* [为什么是任务队列](http://www.slideshare.net/bryanhelmig/task-queues-comorichweb-12962619) 
  是一篇介绍什么是任务队列以及为何需要它们的文章。

* Flask 例子 [使用 Redis 任务队列](https://realpython.com/blog/python/flask-by-example-implementing-a-redis-task-queue/)
  说明了在工作者中设置和使用 Redis RQ 的详细过程。
  
* [如何在 RabbitMQ 中使用 Celery](https://www.digitalocean.com/community/articles/how-to-use-celery-with-rabbitmq-to-queue-tasks-on-an-ubuntu-vps)
  是一篇介绍在 Ubuntu VPS 上使用这些工具的详细教程。

* Heroku 中有一篇详细的教程说明了如何使用 
  [RQ 实现后台任务运行](https://devcenter.heroku.com/articles/python-rq)。

* [在 Python+Django 中使用 Celery 介绍](http://www.linuxforu.com/2013/12/introducing-celery-pythondjango/) 
  提供了针对 Celery 任务队列的介绍。
  
* [Celery 最佳实践](https://denibertovic.com/posts/celery-best-practices/)
  说明了一些你使用 Celery 不可以做的事情，并且展示了一些未充分使用的 Celery 特性来让你的工作更加容易。

* 由 [Rob Golding](https://twitter.com/robgolding63) 编写的“在生产环境中使用 Django”系列中包含一篇专门介绍 [后台任务](http://www.robgolding.com/blog/2011/11/27/django-in-production-part-2---background-tasks/) 的文章。

* [Web 应用中使用异步处理（第一部分）](http://blog.thecodepath.com/2012/11/15/asynchronous-processing-in-web-applications-part-1-a-database-is-not-a-queue/) 
  和 [第二部分](http://blog.thecodepath.com/2013/01/06/asynchronous-processing-in-web-applications-part-2-developers-need-to-understand-message-queues/)
  是理解任务队列与为什么你不应该在你的数据库中使用单一任务区别的优秀阅读材料。

* Caktus Group 的博文 [在生成环境中使用 Celery](http://www.caktusgroup.com/blog/2014/09/29/celery-production/)
  讲解了很多来自他们的良好实践经验，包括在 RabbitMQ 中使用 Celery、使用监控工具以及其它一些在现有文档中并不常见方方面面知识。
  
* [Celery 4 分钟介绍](https://www.youtube.com/watch?v=68QWZU_gCDA) 是一个介绍任务队列的简短视频。

* Heroku 有一篇文章说明了当任务在非加密的网络中发送时，如何
  [为 Celery 提供安全保障](https://engineering.heroku.com/blogs/2014-09-15-securing-celery)。
  
* Miguel Grinberg 写了一篇有关
  [在 Flask 中使用 Celery 任务队列](http://blog.miguelgrinberg.com/post/using-celery-with-flask) 的优秀文章。
  他概要地介绍了设置任务队列的特定代码，从而把任务队列集成到 Flask中。

* 当你是一个使用 Celery 任务队列的新手时，你需要记住这 [3 个 Celery 使用陷阱](https://wiredcraft.com/blog/3-gotchas-for-celery/)。

* [Celery 3.1, Django 1.7 和 Redis 配合使用延期任务和周期任务](https://godjango.com/63-deferred-tasks-and-scheduled-jobs-with-celery-31-django-17-and-redis/)
  是一个用代码展示如何将 Redis Celery 设置为 Django 应用代理中间件的视频。

* [在 Django 中使用 Redis Celery 设置异步任务](http://michal.karzynski.pl/blog/2014/05/18/setting-up-an-asynchronous-task-queue-for-django-using-celery-redis/)
  是一个简单的教程，它讲解了为 Django web 应用设置 Celery 任务队列，并使用 Redis 作为后端代理。

* [ Django 中使用 Celery 实现后台任务](http://django.zone/blog/posts/background-jobs-django-and-celery/)
  配合代码简要说明了如何在 [Django](/django.html) 中使用 Celery。

* [Django 和 Celery 实现异步任务](https://realpython.com/blog/python/asynchronous-tasks-with-django-and-celery/)
  说明了如何将 Celery 集成到 [Django](/django.html) 中，并创建周期性的任务。

* [使用 Celery 两年所总结的三个小技巧](https://library.launchkit.io/three-quick-tips-from-two-years-with-celery-c05ff9d7f9eb)
  提供了关于 Celery 在重试延时、Ofair 标志和全局任务超时三个方面的中肯建议。

## 任务队列学习清单
1. 从你的项目中选择一个在 HTTP 请求期间执行缓慢的函数。

1. 确定你能否在一个固定的时间间隔中预先计算出结果，而不是在 HTTP 请求发生时再计算。如果可以的话，再在别处创建一个可以调用的函数，再将预先计算好的值存储到数据库中。

1. 阅读 Celery 的文档以及相关资源一节列出的链接文章来理解这个项目是如何工作的。

1. 安装一个消息代理中间件，如 RabbitMQ 或者 Redis，然后将 Celery 添加到你的项目中。配置 Celery 从而让它可以和安装的消息代理中间件一起工作。

1. 使用 Celery 周期性地调用来自步骤一中的函数。

1. 让 HTTP 请求函数使用预先计算好的值，而不是像它之前那样依赖运行缓慢的代码获得结果。
