title: Twilio
category: page
slug: twilio
sortorder: 0604
toc: False
sidebartitle: Twilio
meta: Twilio API 允许开发人员将电话拨打、短信发送和视频等通讯功能加入到 Python 应用中。
updated: 2016-09-13


# Twilio
[Twilio](https://www.twilio.com/docs/quickstart/python/twiml) 是一种 [Web 应用编程接口 (API)](/application-programming-interfaces.html)，软件开发人员可以利用它来将 [电话拨打](https://www.twilio.com/docs/tutorials/walkthrough/browser-calls/python/django), [短信发送](https://www.twilio.com/docs/tutorials/walkthrough/server-notifications/python/django), [视频](https://www.twilio.com/docs/api/video/guide/quickstart-js) 及 [双因子认证](https://www.twilio.com/docs/tutorials/walkthrough/two-factor-authentication/python/flask) 等通讯功能加入到他们的 [Python](/learning-programming.html) 应用中。

<img src="/img/twilio-logo.png" width="100%" alt="Twilio logo." class="technical-diagram" style="padding: 10px 0 10px 0;"/>


## 为什么 Twilio 是一个好的 API 选择？

如果你不知道像会话初始化协议（SIP）等的专门通讯协议，不使用 Twilio 与标准电话网络进行交互，并发送和接收电话和短信是极其困难的。Twilio 的 API 对通讯部分进行了抽象，从而作为一个开发者，你只需在你的应用中使用你熟悉的编程语言和框架。例如，这里是如何[发送短信](https://www.twilio.com/docs/quickstart/python/sms/sending-via-rest) 的例子，只用了几行 Python 代码：

    # 导入 Twilio 辅助库 (通过 pip install twilio 进行安装)
    from twilio.rest import TwilioRestClient

    # 将下面代码行中的占位符替换成
    # 你的 Twilio 帐号 SID 及从 Twilio Console 中获取的 Auth Token
    client = TwilioRestClient("ACxxxxxxxxxxxxxx", "zzzzzzzzzzzzz")

    # 将 "from_" 号码修改成你的 Twilio 号码并将 "to" 号码
    # 修改成你想发送短信的任意手机号码
    client.messages.create(to="+19732644152", from_="+12023358536", 
                           body="Hello from Python!")


在 [如果使用 Python 发送短信教程](/blog/send-sms-text-messages-python.html) 中学习关于上面代码的更多知识。

## Twilio 为 Python 开发人员编写的文档怎么样？

Twilio 是一家技术型公司，不是一个传统企业，因此它们的教程和 [文档](https://www.twilio.com/docs) 都是由开发人员编写的。


### 关于 Twilio 的更多资源

* 大部分的 [Twilio 教程](https://www.twilio.com/docs/tutorials) 都有相应的 Python 版本，并附有用 [Django](/django.html) 和 [Flask](/flask.html) 写的完全开源的应用程序。

* [用 Python 自动化枯燥的事务](https://automatetheboringstuff.com/) 中包含有 [发送短信的一个章节](https://automatetheboringstuff.com/chapter16/)，它使用 Twilio 来实现。

* IBM Bluemix 博客上有一篇很精彩的教程，讲述了[使用 Raspberry Pi 和 Bluemix 来创建一个 IoT Python 应用](https://developer.ibm.com/bluemix/2015/04/02/tutorial-using-a-raspberry-pi-python-iot-twilio-bluemix/)，里面使用 Twilio 与 Raspberry Pi 交互。

* [Twilio 博客上的 Python 标签上](https://www.twilio.com/blog/tag/python) 提供了当你构建自己的项目时可供学习的 [Django](https://www.twilio.com/blog/2015/12/city-chat-with-python-django-and-twilio-ip-messaging.html)、[Flask](https://www.twilio.com/blog/2015/11/international-space-station-notifications-with-python-redis-queue-and-twilio-copilot.html) 和 [Bottle](https://www.twilio.com/blog/2016/08/getting-started-python-bottle-twilio-sms-mms.html) 应用。

* [Google Cloud 推荐开发人员在他们的应用中使用 Twilio 进行通讯](https://cloud.google.com/appengine/docs/python/sms/twilio) ，并为 Python 开发人员提供了一份简短的演示。

* [SMS 跟踪提醒](https://www.easypost.com/sms-tracking-tutorial) 是一个很有趣的教程，它整合了两种 API - Twilio 和 [Easypost](https://www.easypost.com) 来跟踪在 Easypost 服务网络上发送的包裹。


#### 免责声明
我 [目前在 Twilio 工作](/about-author.html), 是一位 [开发者布道者](https://www.twilio.com/blog/2014/02/introducing-developer-evangelist-matt-makai.html)。
