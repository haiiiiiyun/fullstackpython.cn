title: Flask
category: page
slug: flask
sortorder: 0404
toc: False
sidebartitle: Flask
meta: Flask 是一个流行的，可扩展的 Web 微框架。
authors: haiiiiiyun.github.io
updated: 2016-06-15 12:20

# Flask
[Flask](http://flask.pocoo.org/) 是一个 Python Web 框架，它在设计实现时奉行 [小核心且易于扩展的哲学](http://flask.pocoo.org/docs/design/)。

<a href="http://flask.pocoo.org/" style="border: none;"><img src="/img/flask.jpg" width="100%" alt="Official Flask logo. Flask Artwork License." class="technical-diagram"></a>


## 为什么说 Flask Web 框架是一个不错的选择？
人们认为 Flask 相比 Django 更加的 [Pythonic](http://blog.startifact.com/posts/older/what-is-pythonic.html)， 因为 Flask Web 应用的代码在多数情况下都会更加清晰明确。 由于创建和运行一个简单的 Flask 应用只需很少的样板文件， Flask 对于初学者来说，更易于上手。

例如，下面是一个 Flask 版本的 "hello world" 应用(它的 Django 版本将需要更多的代码量）：

    from flask import Flask
    app = Flask(__name__)

    @app.route('/')
    def hello_world():
        return 'Hello World!'

    if __name__ == '__main__':
        app.run()

Flask 是距 Django 好几年后才开发的，因此它能从 Django 框架的发展历程中学到很多东西。Jökull Sólberg 在他的这篇文章 [从 Flask 换回到 Django 经历](http://jokull.calepin.co/my-flask-to-django-experience.html)中就很好地阐明了这个问题。

<div class="well see-also">Flask 是对<a href="/web-frameworks.html">Web 框架</a> 概念的一种实现。在 <a href="/web-development.html">Web 开发</a> 那一章你可以了解框架的各部分组件是如何协同工作的，或者到 <a href="/table-of-contents.html">总目录</a> 页去查看其它所有主题。</div>


## Flask 资源
* 由 [Miguel Grinberg](https://twitter.com/miguelgrinberg) 写的这套教程是学习如何使用这个 Web 框架的绝佳入门资源。 每一篇文章都只关注一个主题，并且都是建立在之前文章的基础上。这个系列共分 18 个部分：
  [#1 Hello World](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-i-hello-world)、 [#2 模板](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-ii-templates)、 [#3 表单](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-iii-web-forms)、 [#4 数据库](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-iv-database)、 [#5 用户登录](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-v-user-logins)、 [#6 简介页与用户标识](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-vi-profile-page-and-avatars)、 [#7 单元测试](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-vii-unit-testing)、 [#8 关注者、联系人及好友](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-viii-followers-contacts-and-friends)、 [#9 分页](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-ix-pagination)、 [#10 全文检索](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-x-full-text-search)、 [#11 邮件支持](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-xi-email-support)、 [#12 改良](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-xii-facelift)、 [#13 日期和时间](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-xiii-dates-and-times)、 [#14 国际化和本地化](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-xiv-i18n-and-l10n)、 [#15 Ajax](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-xv-ajax) [#16 调试、测试及性能分析](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-xvi-debugging-testing-and-profiling) [#17 在 Linux 上部署](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-xvii-deployment-on-linux-even-on-the-raspberry-pi) 及 [#18 在 Heroku 云上部署](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-xviii-deployment-on-the-heroku-cloud)。 Miguel 还编写了 [O'Reilly Flask Web 开发](http://shop.oreilly.com/product/0636920031116.do) 这本书，这也是本相当不错的学习资料。

* 如果你想一份趣味教程来学习 Flask 和 WebSocket 知识，看下我的博文 [使用 Reveal.js、 Python 和 WebSocket 创建一个可交互的演示文稿](https://www.twilio.com/blog/2014/11/choose-your-own-adventure-presentations-with-reveal-js-python-and-websockets.html)。参照那个教程来 [创建一个管理界面， 这是第 1 部分](https://www.twilio.com/blog/2015/03/choose-your-own-adventures-presentations-wizard-mode-part-1-of-3.html)、 [第 2 部分](https://www.twilio.com/blog/2015/05/choose-your-own-adventure-presentations-wizard-mode-part-2-of-3.html) 和 [第 3 部分](https://www.twilio.com/blog/2015/07/choose-your-own-adventure-presentations-flask-reveal-js-websockets.html) 向你展示了如何使用表单和 SQLAlchemy。当然这个应用还有一个开源的 [GitHub 代码库](https://github.com/makaimc/choose-your-own-adventure-presentations)，并同步博客 [对每一次的文章发布都作了 tag](https://github.com/makaimc/choose-your-own-adventure-presentations/releases)。

* 这个 [简单的 Flask 应用使用 Twilio Voice](https://www.twilio.com/blog/2015/09/warm-phone-call-transfers-with-python-flask-and-twilio-voice.html) 实现三方之间的语言通话功能。这是我发布在 Twilio 博客上的关于 Python 和 Flask 的介绍文章，非常有趣。

* [Flask 扩展中心](http://flask.pocoo.org/extensions/) 这份精心整理的列表上都是些 Flask 最佳扩展。如果你需要的一些功能没有包含在核心框架中，你可以先到这里找找看。

* [探索 Flask](http://exploreflask.com/) 是一本公共图书，它之前是 Kickstarter 上的一个项目，在进行开源之前大约收费了一年多时间。该书讲解了创建 Flask 应用的最佳实践和模式。 

* [如何组织我的 Flask 应用](http://mattupstate.com/blog/how-i-structure-my-flask-applications/) 演示了这位开发者对其 Flask 应用的各部件和构架是如何进行组织的。

* Jeff Knupp 写了一篇不错的文章叫 [创建一个 Flask 应用](http://www.jeffknupp.com/blog/2014/01/29/productionizing-a-flask-application/)。

* Plank & Whittle 这个博客上有两篇文章，一篇叫 [如何打包一个 Flask Web 应用](http://www.plankandwhittle.com/packaging-a-flask-web-app/)，另一篇叫 [将 Flask 应用打包成一个 Debian 包](http://www.plankandwhittle.com/packaging-a-flask-app-in-a-debian-package/)，适合已创建了一个应用并想进行部署的你看。

* 这份 [Flask 教程](http://code.tutsplus.com/tutorials/an-introduction-to-pythons-flask-framework--net-28822) 是另一个不错的框架入门资料。

* [创建你自己的类似 Yo 的极简消息应用](http://readwrite.com/2014/07/11/one-click-messaging-app) 示范了一个非常基本的 Flask 应用，使用 [Nitrous.io](https://www.nitrous.io/) 来创建项目，并用 [Twilio](https://www.twilio.com/) 来提供短信功能。

* 这个博客系列文章 "其实并不神奇"，讲解了 Flask 中无处不在的 @app.route 这个装饰器到底是如何运作的。这个系列分为两部分， [第 1 部分](http://ains.co/blog/things-which-arent-magic-flask-part-1.html) 和 [第 2 部分](http://ains.co/blog/things-which-arent-magic-flask-part-2.html)。

* [通过示例学 Flask: 第 1 部分](http://www.realpython.com/blog/python/flask-by-example-part-1-project-setup/) 对 Flask 工程如何进行初始设置进行了讲解。 [第 2 部分](http://www.realpython.com/blog/flask-by-example-part-2-postgres-sqlalchemy-and-alembic/) 讲解了如何使用 PostgreSQL、 SQLAlchemy 和 Alembic。 [第 3 部分](https://realpython.com/blog/python/flask-by-example-part-3-text-processing-with-requests-beautifulsoup-nltk/) 描述了如何使用 BeautifulSoup 和 NLTK 进行文本处理。[第 4 部分](https://realpython.com/blog/python/flask-by-example-implementing-a-redis-task-queue/) 展示了如何用 Flask 和 Redis 来创建一个任务队列。

* [使用 Python 和 Twilio 生成品牌的彩信优惠券](https://www.twilio.com/blog/2014/10/branded-mms-coupon-generation-with-python-and-twilio.html) 是我写的一篇 Flask 教程，讲述如何创建一个 Web 应用并通过彩信发送品牌条码优惠券。这篇文章对应用开发的每个步骤（从一片空目录开始直到创建一个可以部署到 Heroku 的应用）都作了一一的讲解。

* [如何组织一个大型的 Flask 应用](https://www.digitalocean.com/community/articles/how-to-structure-large-flask-applications) 涉及的这个主题，是你一旦要开始在你的 Flask 应用 中增加重要的功能时就会很快碰到的。

* [Flask 模板](http://fewstreet.com/2015/01/16/flask-blueprint-templates.html) 针对大型项目，展示了如何组织你的多个 [blueprints](http://flask.pocoo.org/docs/0.10/blueprints/)。

* [Flask 实现视频流功能](http://blog.miguelgrinberg.com/post/video-streaming-with-flask) 是 Miguel Grinberg 的另一篇精彩教程，内容涉及视频流。

* [一行代码并能减少 Flask 60% 的页面加载时间](https://medium.com/@5hreyans/the-one-weird-trick-that-cut-our-flask-page-load-time-by-70-87145335f679) 是篇重要的文章，阐明了优化 Flask 模板的缓存大小在某些情况下能显著地增加性能。

* [利用 Python 的 Flask 和 Nose 来对你的 Twilio 应用进行单元测试](https://www.twilio.com/blog/2014/03/unit-testing-your-twilio-app-using-pythons-flask-and-nose.html) 涉及如何将 Twilio API 集成到 Flask 应用中，以及如何用 [nose](https://nose.readthedocs.org/en/latest/) 进行功能测试。

* Flask 文档上有一些小例子，演示了如果在 [独立的 WSGI 容器](http://flask.pocoo.org/docs/deploying/wsgi-standalone/) 中部署 Flask。

* [在 Flask 中如何确认邮件地址](https://realpython.com/blog/python/handling-email-confirmation-in-flask/) 很好地示范了如何将邮件地址与用户的登录信息进行匹配。

* 如果你还不是很了解为什么在生产环境中 [部署](/deployment.html)后，必须要将 `DEBUG` 设置成 `False` 的话，你应该读读这篇文章 [Patreon 是如何被黑掉的](http://labs.detectify.com/post/130332638391/how-patreon-got-hacked-publicly-exposed-werkzeug)。


## 开源 Flask 示例项目
* [交互式的演示文稿](https://github.com/makaimc/choose-your-own-adventure-presentations) 将 Flask 与 [Reveal.js](http://lab.hakim.se/reveal-js/) 及短信结合，创建了一个观众能够投票决定事件进程的演示文稿。它的代码在 MIT 许可下完全开源，它使用 [Flask-SocketIO](https://flask-socketio.readthedocs.org/en/latest/) 和 [Flask-WTF](https://flask-wtf.readthedocs.org/en/latest/) 项目来支持投票和表单输入功能。

* [Skylines](https://github.com/skylines-project/skylines) 是一个开源的航班信息追踪系统，它用 Flask 实现。可以在 [这里看到这个应用的运行效果](https://skylines.aero/)。

* [Microblog](https://github.com/miguelgrinberg/microblog) 这个开源项目是和 Miguel Grinberg 的 O'Reilly Flask 那本书配套的。

* [Flaskr TDD](https://github.com/mjhea0/flaskr-tdd) 遵循了官方的 Flask 教程， 并在项目中增加了测试驱动开发和 JQuery。

* 这是一个 [笔记记录应用](http://charlesleifer.com/blog/saturday-morning-hack-a-little-note-taking-app-with-flask/)，这是它在 [Gist 上的源代码](https://gist.github.com/coleifer/632d3c9aa6b2ea519384)。

* [Bean Counter](https://github.com/BouncyNudibranch/bean-counter) 是一个开源的 Flask 应用，用于追踪咖啡的相关信息。

* [FlaskBB](http://flaskbb.org/) 是一个用 Flask 实现的论坛应用。

* [psdash](https://github.com/Jahaja/psdash) 这个应用是用 Flask 和 psutils 创建的，它能显示运行它的计算机的相关信息。


## Flask 项目模板
* [Flask App Engine 模板](https://github.com/kamalgill/flask-appengine-template) ，采用这个模板设置，你的 Flask 应用就能在 Google App Engine 上运行。

* [Flask Foundation](https://github.com/JackStouffer/Flask-Foundation) 是一个 Flask 项目模板。它还有一个 [相应的网站](https://jackstouffer.github.io/Flask-Foundation/)，讲解了这个模板中包含了哪些扩展。

* [Cookiecutter Flask](https://github.com/sloria/cookiecutter-flask) 这个项目模板使用了 [Cookiecutter](https://github.com/audreyr/cookiecutter)。

* [Flask-Boilerplate](https://github.com/MaxHalford/Flask-Boilerplate) 是另一个项目模板，它提供了注册、登录和密码重置等功能。


## Flask 框架学习清单
1. 在你的本地开发机上 [安装 Flask](http://flask.pocoo.org/docs/installation/) 。

1. 根据上面的 “Flask 资源”节里列出的那 18 个 Flask 教程，依次练习。
 
1. 在 [Flask 扩展中心](http://flask.pocoo.org/extensions/) 查找你的项目所需的扩展。

1. 在学习和研究完那 18 个 Flask 教程以及下面列出的开源示例应用后，开始编写你自己的 Flask 应用 。

1. 查看 [部署那一章](/deployment.html)，将你的 Flask 项目发布上网上。
