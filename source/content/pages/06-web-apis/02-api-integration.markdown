title: API 集成
category: page
slug: api-integration
sortorder: 0602
toc: False
sidebartitle: API 集成
meta: Web API 集成对于手机应用和 Web 应用都是必要的。到 Full Stack Python 上学习更多关于 API 集成的知识。
authors: haiiiiiyun.github.io
updated: 2016-07-27 16:49--20:27


# API 集成
大部分生产环境中的 Python Web 应用都依赖一些外部托管的应用程序编程接口 (API)。API 也通常被称作第三方服务或外部平台。 这样的例子包括提供信息和语音服务的 [Twilio](https://www.twilio.com/docs/)，提供支付处理的 [Stripe](https://stripe.com/docs/api) 和提供嵌入网页的评论功能的 [Disqus](https://disqus.com/api/docs/)。

关于如何合理设计 API 的文章相对较多，然而有关 API 集成最佳实践的文章却很少。但是，因 API 为许多实现领域提供了关键功能，该主题的重要性正在持续提高。


## 托管的 API 测试服务
* [Runscope](https://www.runscope.com/) 是专门为 API 设计的一项服务，它能辅助开发人员进行自动化测试和流量监视。

* [Apiary](http://apiary.io/) 能为 API 的创建提供蓝图，从而使人们能更加容易地进行测试并创建出清晰的文档。


## API 集成相关资源
* 相比 API 的辅助库，一些开发人员更喜欢使用 [Requests](http://docs.python-requests.org/en/latest/)。如果那样，不妨看下 [关于如何使用 requests 访问 Web APIs 的教程](http://engineering.hackerearth.com/2014/08/21/python-requests-module/) 这篇文章。

* Product Hunt 列出了大量常用的 [收费和免费 Web APIs](https://www.producthunt.com/e/an-api-for-everything)，说明了 “API 无处不在”。

* [18F API-All-the-X 列表](http://18f.github.io/API-All-the-X/) 收集了所有政府发布的 Web API。当有新的 API 上线时，这份列表也会作相应的更新。

* 如果你使用 Requests，不妨看下这篇简洁实用的指南，[如何使用 Python 对 HTTP 错误进行优雅地处理](http://www.mobify.com/blog/http-requests-are-hard/)。

* John Sheehan 的 "[API 维护之禅与艺术](https://speakerdeck.com/johnsheehan/zen-and-the-art-of-api-maintenance)" 这个幻灯片是有关 API 集成的。

* Randall Degges 的 "[API 驱动的开发](https://stormpath.com/blog/api-driven-development/)" 这篇文章讲解了 API 的使用如何能减少你需要编写的代码量及维护量，从而使你能更快地完成应用开发。

* [确保第三方 API 使用时的安全性](http://www.slideshare.net/SmartBear_Software/safe-sex-with-thirdparty-apis) 这篇文章非常有趣，它高度总结了当你的应用需要使用第三方服务时，你应该如何做才能确保安全性。

* [在 Requests 中进行重试操作](http://www.coglib.com/~icordasc/blog/2014/12/retries-in-requests.html) 是篇不错的教程，讲述了如何使用 Requests 这个库来轻松地对失败的 HTTP 请求进行重新尝试。

* 我在 DjangoCon 2013 上专门讲述了 "[如何使 Django 能与第三方服务更好集成](http://www.youtube.com/watch?v=iGP8DQIqxXs)。"

* 如果你想找一个使用了两种 Web API 的 Django 应用项目示例，不妨参照这个教程，[使用 Django、MMS 和 PokéAPI 来创作你自己的 Pokédex](https://www.twilio.com/blog/2014/11/build-your-own-pokedex-with-django-mms-and-pokeapi.html)。

* [vcr.py](https://www.brianthicks.com/2014/12/01/test-apis-properly-with-vcr-py/) 是捕获并重新执行带模拟数据的 HTTP 请求的一种方法。它对于 API 集成非常有用。

* [缓存外部 API 请求](https://realpython.com/blog/python/caching-external-api-requests/) 是一篇很好的文章，讲述了当使用 Requests 库访问外部 Web API 时，如何才能最大限度地减少 HTTP 调用所需的次数。


## API 集成学习清单
1. 挑选一个具有一流文档的 API。这里有一份 [非常适合初学者的十种 API](https://medium.com/she-hacks-hacker-academy/4d3c43be9386)。

1. 查阅你所选 API 的相关文档。找到通过使用 API 能对你的应用有所改善的地方。

1. 在开始写代码前，先使用命令行中的 [cURL](http://curl.haxx.se/) 或者浏览器中的 [Postman](http://www.getpostman.com/) 对该 API 进行练习。通过练习有助于你更好地掌握 API 认证以及请求与返回所需数据的相关知识。

1. 评估是要用一个辅助库，还是用 [Requests](http://docs.python-requests.org/en/latest/)。辅助库通常更易使用，而 Requests 可使你对 HTTP 调用施加更多控制。

1. 将 API 调用移到 [任务队列](/task-queues.html)，从而使其不会阻塞 Web 应用的 请求-应答 流程。
