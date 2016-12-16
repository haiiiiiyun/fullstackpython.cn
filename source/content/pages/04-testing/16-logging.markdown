title: 日志
category: page
slug: logging
sortorder: 0714
toc: False
sidebartitle: 日志
meta: 日志可将错误、警告以及事件输出保存到存储器中，方便后期调试。快来 Full Stack Python 学习更多有关日志的知识吧。
translators: blog.chriscabin.com
updated: 2016-07-23 08:00


# 日志
日志将诸如错误、警告以及事件信息保存到永久存储器中，以便后期调试。


## 日志为何很重要？
将中断代码运行的异常信息通过日志输出是非常重要的，它可以用来观察并修复源码问题。
此外，信息日志和调试日志也可以帮助理解应用程序是如何执行的，即使代码能够正常工作。

## 日志等级
日志通常分为四类：

1. 信息
1. 调试
1. 警告
1. 错误

当 web 框架在运行时通过日志输出出错信息，对于理解你的应用是如何执行的是至关重要的。

## 日志聚合器
当你的应用运行在多个服务器上时，拥有一款叫做“日志聚合器”的工具是非常有帮助的。你可以配置你的应用程序将系统和应用日志重定向到一个地点，在那儿有很多工具用于查看、搜索以及监控你的集群服务器上的日志事件。

使用日志聚合器工具的另外一个优势是，它们允许你自定义设置警报，这样当错误率超出某个阈值时就能获得警报通知。

### 开源日志聚合器
* [Sentry](https://github.com/getsentry/sentry) 起初只提供 Django 异常处理服务，但现在拥有几乎所有主要编程语言和框架的对应日志客户端。它仍然可以和 Python 驱动的 web 应用工作的很好，并且通常用于和其它监控工具连接。[Raven](http://raven.readthedocs.org/en/latest/) 是用于 Sentry 的开源 Python 客户端。

* [Graylog2](http://graylog2.org/) 提供了一个用于日志聚合的中央服务器，以及一个用于浏览和搜索日志事件的图形化工具。它拥有针对大多数主要语言的库，包括 Python。它把数据保存在 Elasticache。

* [Logstash](http://logstash.net/) 与 Graylog2 类似，它提供一些通过编程控制日志数据流的特性。

* [Scribe](https://github.com/facebook/scribe) 是一个由 Facebook 实现的日志聚合器项目。它旨在运行于多个服务器上，并能够根据你剩余的集群进行扩展。它使用 Thrift 消息格式，所以可以用于任何语言。


### 托管的日志服务
* [Loggly](https://www.loggly.com/) 是一个第三方基于云的日志聚合器应用。它们提供了针对每种主要语言的说明，包括 Python。它还在自定义搜索中提供了邮件警报的功能。

* [Splunk](http://www.splunk.com/) 用于事件聚集，提供了第三方云以及自定义托管的方案。它擅长于搜索以及对任何基于文本数据的数据挖掘。

* [Papertrail](https://papertrailapp.com/) 和 Loggly 和 Splunk 都很像，它提供了集成到 S3 的功能，用于长期存储日志。

* [Raygun](http://raygun.io/) 用于输出错误日志，并且当问题发生时会及时报告。

* [Scalyr](https://www.scalyr.com/) 在标准日志层面上添加了用户界面，提供了日志聚集、面板操作、警报以及搜索等功能。

* 若是你没时间设置开源版本的 Sentry 的话，这儿有一个 [托管版本的 Sentry](https://www.getsentry.com/welcome/)。

## 日志相关资源
* 这篇 
  [介绍日志](http://www.blog.pythonlibrary.org/2012/08/02/python-101-an-intro-to-logging/) 的文章演示了如何使用 Python 的日志模块。

* [像讲故事一样看待日志](https://clusterhq.com/2013/12/04/logging-storytelling/)
  拥有多个系列，它采用类比的方式说明阅读日志应当像阅读故事一样，从而让你能够更好地理解你的 web 应用正在发生什么。
  [第二部分：描述动作](https://clusterhq.com/2014/01/21/logging-storytelling-lets-add-action/)
  还有 
  [第三部分：讨论类型](https://clusterhq.com/2014/03/25/logging-storytelling-3-types/)。

* [一个有关日志的简要题外话](https://lukasa.co.uk/2014/05/A_Brief_Digression_About_Logging/)
  是一篇简短的文章，讲解了如何设置 Python 日志并快速运行起来。
  
* [摆脱 Python 日志的痛苦](https://hynek.me/articles/taking-some-pain-out-of-python-logging/)
  说明了如何在 uWSGI 中设置日志。

* [Python 日志最佳实践](http://victorlin.me/posts/2012/08/26/good-logging-practice-in-python)
  说明了如何使用标准的日志模块从的应用中输出日志数据。这绝对是一篇值得阅读的文章，因为多数应用程序都没能输出足够多的日志信息，用于在出错时帮助开发者调试或者做决策。

* Django 1.3 发行版为项目带来了统一标准的日志配置。这篇文章说明了如何在项目的 settings.py 文件中 [设置日志](http://www.djm.org.uk/how-to-log-file-django-13-and-above/)
  Caktus 也有一篇非常棒的教程说明了
  [使用 graypy 和 Graylog2 聚集日志](http://www.caktusgroup.com/blog/2013/09/18/central-logging-django-graylog2-and-graypy/)。

* [Django 日志配置：默认设置是如何干扰你的？](http://www.caktusgroup.com/blog/2015/01/27/Django-Logging-Configuration-logging_config-default-settings-logger/)
  指出了使用 Django 默认日志配置的一个问题，并说明了在你的项目中该为此做些什么。

* [Python 异常日志](https://www.loggly.com/blog/exceptional-logging-of-exceptions-in-python/)
  说明了如何用日志输出更加精确的错误信息来定位问题，而非在日志中接收通用的异常信息。

## 日志学习清单
1. 阅读材料学习如何在你的 web 应用框架中集成日志输出的功能。

1. 确保错误和异常都被日志输出了。虽说这些日志可以采用 [监视器](/monitoring.html) 方案存储，但最好还是能拥有你自己的日志存储位置，这样便于在问题发生时调试，并且也能作为其它监视器系统的补充。

1. 为你可能需要使用的系统事件集成日志输出功能以便后期调试。例如，当函数超出某个阈值时，你可能想知道它们的返回值。

