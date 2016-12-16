title: 应用程序编程接口
category: page
slug: application-programming-interfaces
sortorder: 0601
toc: True
sidebartitle: 6. Web APIs
meta: Web 应用编程接口 (APIs) 为数据在机器间传输提供了一种机制。到 Full Stack Python 上学习有关 API 的更多知识。
authors: haiiiiiyun.github.io
updated: 2016-07-27 21:24--23:09


# 应用程序编程接口
应用程序编程接口 (APIs) 使得应用程序间能进行数据转移和信号交换。


## API 为什么重要？
HTML、 CSS 和 JavaScript 为人类创建网页。但是，这些页面难以被机器使用。

有很多的抓取工具或库可以用来提取 HTML 页面中的数据，但是通过 API 来获取数据会更加容易。例如，要想获取一篇新闻内容，通过 API 来获取比从 HTML 页面中提取会更加容易。

## API 关键概念
API 的世界里有几个关键概念。在深入研究 API 之前最好把它们都弄明白先。

* 表述性状态转移 (REST)

* Webhooks

* JavaScript 对象标记 (JSON) 及可扩展标记语言 (XML)

* Endpoints


## Webhooks
一个 Webhook 就是由用户定义的 一个 HTTP 回调 URL，它会在系统条件满足时被调用。回调会以 POST 或 GET 请求的方式进行，通常也进行传输数据，从而知会其它系统。

Webhooks 之所以重要是因为它们能为 API 开启双向通讯。Webhook 的便捷性，源自它是由 API 用户定义的，而非 API 本身定义。

例如，在 [Twilio API](https://www.twilio.com/api) 中，当一条短信发送到 Twilio 的手机号码后，Twilio 会向用户指定的某个 URL 发送一条 HTTP POST 请求。该 URL 通过 Twilio 号码页上的一个文本框进行定义，如下图所示。

<img src="/img/twilio-webhook-definition.jpg" width="100%" alt="在 Twilio APi 中定义的 Webhook。" class="technical-diagram" />


## API 开源项目
* [Swagger](https://github.com/wordnik/swagger-core) 是一个用 Scala 编写的开源项目，它为 RESTful API 定义了一个标准接口。


## API 相关资源
* [Zapier](https://zapier.com/) 上有一份免费指南叫 [APIs 101](https://zapier.com/blog/apis-101/)，讲述了什么是 API，为什么它们很有价值及如何正确使用。

* [GET PUT POST](https://medium.com/get-put-post) 是一份专注于 API 知识的时讯。已发行版中包含有对 Stripe、 Dropbox 和 Coinbase 开发人员的采访。

* [RESTful 到底是什么](https://codewords.recurse.com/issues/five/what-restful-actually-means) 用平实的语言对 REST 的原理进行了精彩的讲解，并讲述了它们进化到当前状态的相关历史背景。

* 由 [Nick Quinlan](https://twitter.com/YayNickQ) 写的 [什么是 webhook？](https://sendgrid.com/blog/whats-webhook/) 这篇文章，用平实的语言解释了什么是 Webhook，以及为什么它们在 API 世界中有必要存在。 

* [简单性和实用性，或者，为什么 SOAP 衰败了](http://keithba.net/simplicity-and-utility-or-why-soap-lost) 就当前为何基于 JSON 的 Web 服务会比那个在 21 世纪早期曾盛极一时的 SOAP 更流行等问题提供了相关的背景知识。

* [适合各种场合的 API 工具](https://medium.com/@orliesaurus/api-tools-for-every-occasion-10-api-tools-released-in-2015-i-can-t-live-without-d5947d9ca9c3) 列出了 10 个工具列出，它们在处理 API 时真得非常有用，并且都是 2015 年最新的。


## API 学习清单
1. 学习 API 相关概念--使用 JSON、XML、Endpoint 和 Webhook 的机器间通信。

1. 将 API，比如 Twilio 或 Stripe，集成到你的 Web 应用中。阅读 [API 集成](/api-integration.html) 那一章来学习更多相关信息。

1. 使用框架为你自己的应用创建一份 API。到 [API 创建](/api-creation.html) 页学习关于 Web API 框架的相关知识。

1. 将你的 Web 应用 API 公布出来，从而使其它应用能获取你想共享的那些数据。
