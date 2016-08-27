title: 对象关系映射器 (ORMs)
category: page
slug: object-relational-mappers-orms
sortorder: 0504
toc: False
sidebartitle: 对象关系映射器
meta: 对象关系映射器 (ORMs) 在关系型数据库和面向对象的代码间起了连接作用。到 Full Stack Python 上学习更多相关知识。
updated: 2016-07-17
writing-date: 2016-07-13 19:26--2016-07-17 13:20


# 对象关系映射器 (ORM)
对象关系映射器 (ORM) 是一种代码库，它能自动将存储在关系型数据库表中的数据转化成在应用程序代码中更加常用的对象。


## 为什么 ORM 很有用？
ORM 为 [关系型数据库](/databases.html) 提供了高级的抽象，它使得开发人员不必写 SQL，只需写 Python 代码就能在数据库中创建、读取、更新和删除数据。开发人员能使用他们熟悉的编程语言来处理数据库，而无需编写 SQL 语句或存储过程。

例如，如果没有 ORM 的话，开发人员需要编写以下的 SQL 语句来读取 USERS 表中的 ``zip_code`` 列的值为 94107 的所有行：

    SELECT * FROM USERS WHERE zip_code=94107;


而其相应的 Django ORM 查询语句看起来会如下面的 Python 代码：

    # obtain everyone in the 94107 zip code and assign to users variable
    users = Users.objects.filter(zip_code=94107)


编写 Python 代码来代替编写 SQL，能提高 Web 应用的开发速度，特别是在项目前期的时候。开发速度的提升潜力源于无需从编写 Python 代码切换到编写声明式的 SQL 语句。虽然有些开发人员可能不太介意在两种语言间来回切换，但是使用一种编程语言对于捣鼓出一个原型或者开始创建一个 Web 应用通常更加容易。

从理论上来说，ORM 也使得应用程序在不同的关系型数据库之间切换使用变得可能。比如说，开发人员可以在本地开发中使用 [SQLite](/sqlite.html)，然后在生产环境中使用 [MySQL](/mysql.html)。 只需进行少量的代码修改，生产环境中的应用就能实现从 MySQL 切换到 [PostgreSQL](/postgresql.html)。

但在实践中，本地开发环境和生产环境最好使用相同的数据库。不然的话，在本地开发环境从未碰到的一些始料未及的错误可能会出现在生产环境中。而且，对于一个项目来说，很少有需将生产环境中的数据库切换到另一个数据库的情况，除非有很紧急的原由。

<div class="well see-also">学习 ORM 的时候，你也应该学习下 <a href="/deployment.html">部署</a> 和 <a href="/application-dependencies.html">应用依赖</a> 章节。</div>


## 我需要在我的 Web 应用使用 ORM 吗？
Python ORM 库对于存取关系型数据库来说不是必须的。实现上，低层的存取接口通常是由另一个叫 *数据库连接器* 的库来提供的，例如 [psycopg](http://initd.org/psycopg/) (用于 PostgreSQL) 或 [MySQL-python](https://pypi.python.org/pypi/MySQL-python/1.2.5) (用于 MySQL) 等。 下表列出了 ORM 与不同的 Web 框架、连接器及关系型 数据库一起使用的情况。

<img src="/img/orm-examples.png" width="100%" alt="各种 Python ORM 如何能与不同的连接器及后端一起使用的例子。" class="technical-diagram" />

从上面的表格中可以看出，例如，SQLAlchemy 能与不同的 Web 框架和数据库连接器一起使用。开发人员也可以撇开 Web 框架单独使用 ORM，比如在创建一个数据分析工具或者没有用户界面的批处理脚本时。


## 使用 ORM 有什么缺点？
ORM 有很多的缺点，包括：

1. 阻抗失配
1. 有可能降低性能
1. 将复杂性从数据库转移到了应用程序代码中


### 阻抗失配
“阻抗失配” 这个术语通常和 ORM 一起使用。阻抗失配这个术语，是对于数据在关系型数据表与应用程序对象之间变换时的所有难度的总称。其要点是：开发人员使用对象的方式与数据在关系型数据表中如何被存储和关联是有差异的。

[这篇关于 ORM 阻抗失配的文章](http://www.agiledata.org/essays/impedanceMismatch.html) 对该概念进行了细致的综述，并提供图表以可视化方式解析了该问题发生的原因。


### 降低性能的潜在可能
使用任何一个高级抽象或框架，存在的其中一个顾虑是有存在降低性能的潜在可能性。使用 ORM 时，性能影响因素源自：应用代码会被转化成没有被合理调优过的 SQL 语句。

ORM 通常是上手容易但真正掌握很难。比如说，一个 Django 新手无需知道 [`select_related()` function](https://docs.djangoproject.com/en/1.8/ref/models/querysets/#select-related) 及其如何能提升某些外键关联型查询的性能等知识，就能使用 ORM 了。每种 ORM 都有许多有关性能的提示和技巧。花时间学习这些技能比只学习 SQL 及如何编写存储过程可能有用的多。

这章里有许多显而易见的 “可能或可能不” 以及 ”潜在的“ 等字眼。在大型项目中，ORM 非常适用于大约 80-90% 的情况，而项目中剩下 10-20% 的数据库交互操作，可以由经验丰富的数据库管理员编写调优过的 SQL 语句来代码 ORM 生成的 SQL 代码，从而使其性能得到显著提高。


### 将复杂度从数据库转到应用程序代码
我们需要编写一些代码来处理应用的数据。在 ORM 之前，数据库存储过程被用于封装数据库逻辑。而在 ORM 中，操作数据的代码存在于应用的 Python 代码中。这些额外的数据操作逻辑，对于一个设计良好的应用来说，通常都不会成为一个问题，但因其没有在应用程序和数据库存储过程之间将代码进行拆分，从而提高了 Python 的总代码量。


## Python ORM 的实现
存在很多个用 Python 编写的 ORM 实现，包括

1. [Django ORM](https://docs.djangoproject.com/en/1.8/topics/db/)
1. [SQLAlchemy](http://www.sqlalchemy.org/)
1. [Peewee](https://peewee.readthedocs.org/en/latest/)
1. [PonyORM](http://ponyorm.com/)
1. [SQLObject](http://sqlobject.org/)

还有其他一些 ORM, 例如 Canonical 的 [Storm](https://storm.canonical.com/)，但是其中大多数现在看来都已经停止开发了。让我们进一步了解以下几个主要的还活跃着的 ORM 吧。


### Django ORM
[Django](/django.html) Web 框架有自己内置的对象-关系映射模块，通常被称作 "the Django ORM" 或 "Django's ORM"。

[Django 的 ORM](https://docs.djangoproject.com/en/dev/topics/db/) 适用于简单或中等复杂度的数据库操作。但是，人们通常抱怨说：该 ORM 基于复杂的查询操作转化而成的 SQL 语句，相比于直接用 SQL 编写或者用 [SQLAlchemy](http://www.sqlalchemy.org/) 产生的语句，更加的繁琐。

从技术上来说可以直接使用低层的 SQL，但是这种方式会将查询与某个特定的数据库绑定在一起。该 ORM 与 Django 是紧密捆绑的，因而要想用 SQLAlchemy 来代替默认的 ORM 当前还是一门技术活。考虑到一些 Django 核心贡献者都认为默认的 ORM 被 SQLAlchemy 替代只是时间问题。但要想实现该目标还有很多路要走，可能会在 [Django 1.9 或之后](https://github.com/mattmakai/fullstackpython.com/issues/48) 的版本才会实现。

因为大多数 Django 项目都使用默认的 ORM，因此我们最好多了解下一些高级的使用案例和工具，从而能更好地使用该框架。


### SQLAlchemy
[SQLAlchemy](http://www.sqlalchemy.org/) 是个广受好评的 Python ORM。它的抽象层做的 ”恰当好处“，并且在绝大多数情况下，相比 Django ORM，它能简化复杂数据库查询语句的编写工作。在 Flask 中，SQLAlchemy 通过 [Flask-SQLAlchemy](https://pythonhosted.org/Flask-SQLAlchemy/) 扩展而被用作数据库 ORM。


### Peewee
[Peewee](https://peewee.readthedocs.org/en/latest/) 这个 Python ORM 的目标是： 比 SQLAlchemy "[更简单、更小及更加 hackable](http://charlesleifer.com/blog/the-case-for-peewee-small-hackable-and-fun/)" 。Peewee 的核心作者使用的比喻为： Peewee 对于 SQLAlchemy，就像 SQLite 对于 PostgreSQL。一个 ORM 无需适用于所有的使用情况也能被认为是有用的。


### Pony
[Pony ORM](http://ponyorm.com/) 是另一种 Python ORM，它的许可模型有些许不同。该项目使用多种许可。Pony 用于开源项目是免费的，但是用于商业项目需要 [商业许可](http://ponyorm.com/license-and-pricing.html)。该许可只需要一次性费用，无需周期付费。


### SQLObject
[SQLObject](http://sqlobject.org/) 这个 ORM 自 [2003 年前](http://sqlobject.org/News1.html#sqlobject-0-5) 就已处于活跃的开源开发了。



## 模式迁移
模式迁移，例如添加一个列到数据库的某个表格中等操作，从技术上来说都不属于 ORM 范畴。但是，由于 ORM 通常是间接地操作数据库（在多数情况下需开发人员自担风险），因此在应用程序项目中，执行模式迁移的库通常和 Python ORM 一起使用。

数据库模式迁移是一个复杂的主题，需要专门的一页来讲解。现在，我们粗略地将模式迁移相关资源列在 ORM 链接之后。


### 通用 ORM 相关资源
* 还有一个网页就 [什么是 ORM](http://www.agiledata.org/essays/mappingObjects.html) 进行了细致的概述。

* 这个 [GitHub 上的示例项目](https://github.com/sloria/PythonORMSleepy) 将这个相同的 Flask 应用用多个不同的 ORM 进行了实现： SQLAlchemy、 Peewee、 MongoEngine、 stdnet 及 PonyORM。

* Martin Fowler 在一篇文章中提到了 [人们对 ORM 的厌恶](http://martinfowler.com/bliki/OrmHate.html)，讲述了 ORM 是如何被误用的，及说明它们对开发人员其实是有帮助的。

* 如果你被连接器之间的区别搞糊涂了，比如 MySQL-python 和一个像 SQLAlchemy 等的 ORM，那么看下针对这个主题的 [StackOverflow 上的解答](http://stackoverflow.com/questions/2550292/purpose-of-sqlalchemy-over-mysqldb)。


### Django ORM 相关资源
* [Django 数据模型、封装和数据集成](http://www.dabapps.com/blog/django-models-and-encapsulation/) 是一篇由 Tom Christie 写的详实的文章，讲述了如何对 Django 数据模型进行封装以实现数据集成。

* [Django 调试工具栏](http://django-debug-toolbar.readthedocs.org/en/1.2/) 是一个强大的 Django ORM 数据库查询检测工具。非常推荐在开发环境中使用，以确保你所写的查询代码的合理性。 [Django Silk](http://mtford.co.uk/blog/2/) 是另一个检测工作，除了 SQL 检测功能，它还提供其它一些功能。

* [使 Django 应用运行更快](http://reinout.vanrees.org/weblog/2014/05/06/making-faster.html) 是篇讲述 Django 性能的博文，上面有一些有关如何度量性能及如何基于测试结果进行优化的建议。

* [我为什么讨厌 Django ORM](https://speakerdeck.com/alex/why-i-hate-the-django-orm) 是 Alex Gaynor 对于一些不好的设计决策的总结，这些决策都是他在构建 Django ORM 时做出的。

* [超越 Django ORM 与 Postgres](https://speakerdeck.com/craigkerstiens/going-beyond-django-orm-with-postgres) 是专门讲述如果在 Django 中使用 PostgreSQL 的。

* [将一个 Django 应用从 MySQL 迁移到 PostgreSQL](http://www.calazan.com/migrating-django-app-from-mysql-to-postgresql/) 是一篇关于如果从 MySQL 迁移到 PostgreSQL 的粗略介绍。但是我认为，任何一个已经在某个 [关系型数据库](/databases.html) 上运行了一段时候的 Django 应用，要想移植到另一个后端，即便是使用了 ORM，还是需要很多的工作量。

* [Django 数据模型描述子](http://blog.kevinastone.com/django-model-descriptors.html) 讨论并演示了如何通过将业务逻辑合并到 Django 数据模型，从而降低视图的复杂度，它使得代码在各独立的视图间更加易于重用。

* [同时支持 Django 1.7 和 South](http://treyhunner.com/2014/03/migrating-to-django-1-dot-7/) 首先就支持 Django 1.7 与在 Django 1.6 中修护 South 这个迁移工具之间的区别进行了讲解，然后给出了具体解决方法。

* [为你的 Django 网站添加基本的查询功能](https://www.calazan.com/adding-basic-search-to-your-django-site/) 展示了如何通过 Django ORM 编写普通的查询代码，为你的站点提供搜索功能，而无需依赖像 ElasticSearch 等其它工具。它非常适合小型站点，而之后你也可以使用一个更健壮的搜索引擎进行扩展。

* [如何使用 Django 的代理数据库模型](https://www.wellfireinteractive.com/blog/using-django-proxy-models) 这篇文章详细地讲解了 Django ORM 中的一个概念，该概念通常不太会被提及或得到解释。

* [整合 Django 后台系统的登录功能](http://tech.marksblogg.com/django-admin-logins.html) 展示了如何对身份认证失败日志进行记录，如果创建一份 IP 地址白名单，及如何将 fail2ban 与身份认证失败列表结合使用。

* [Django 数据迁移 - 入门](https://realpython.com/blog/python/django-migrations-a-primer/) 带你领略了集成到 Django 1.7 内核中的新的迁移系统，并特别介绍了一个固定的工作流程，该流程可用于创建和实施数据迁移。

* [Django 1.7: 数据库迁移做得对](https://markusholtermann.eu/2014/09/django-17-database-migrations-done-right/) 讲解了为何 South 不能直接集成进 Django 中，迁移是如何创建的并展示了后退迁移是如何工作的。

* [压缩及优化 Django 中的迁移操作](http://www.rkblog.rk.edu.pl/w/p/squashing-and-optimizing-migrations-django/) 以一个简单的示例代码展示了如何使用这个集成到 Django 1.7 中的迁移工具。

* [在 Django 中对带有 NULL 值的查询集进行排序](https://www.isotoma.com/blog/2015/11/23/sorting-querysets-with-nulls-in-django/) 展示了对包含有 NULL 值的列进行排序这个常见问题如何进行处理。


### SQLAlchemy 相关资源
* 如果你对 SQLAlchemy 与 Django ORM 之间的区别感兴趣，我推荐你读下 Armin Ronacher 写的 [SQLAlchemy 和你](http://lucumr.pocoo.org/2011/7/19/sqlachemy-and-you/)。

* [开源应用的体系结构这本书上有完整的一章专门讲述了 SQLAlchemy](http://aosabook.org/en/sqlalchemy.html)。内容很详实，非常值得一读，从中可以了解其低层的工作原理。

* [SQLAlchemy vs 其它 ORM](http://www.pythoncentral.io/sqlalchemy-vs-orms/) 提供了 SQLAlchemy 与其它可替代品的详细对比。

* 大多数 Flask 开发人员使用 SQLAlchemy 作为关系型数据库的 ORM。如果你不太熟悉 SQLAlchemy 的话，你经常会有 [刷新和提交之间有什么不同？](http://stackoverflow.com/questions/4201455/sqlalchemy-whats-the-difference-between-flush-and-commit) 等这样的疑问，领会这些问题对于创建你的应用是至关重要的。

* [SQLAlchemy 与 Django](https://engineering.betterworks.com/2015/09/03/sqlalchemy-and-django/) 讲解了一个开发团队如何用Django ORM 处理大多数情况下的标准查询工作，而在真正高级查询中使用 SQLAlchemy。

### Peewee 相关资源
* [使用 Peewee 进行数据库连接管理](http://charlesleifer.com/blog/managing-database-connections-with-peewee/) 对 ORM 的连接池及 ExecutionContext 进行了讲解。

* [用 Python 实现一个加密命令行日记程序](http://charlesleifer.com/blog/dear-diary-an-encrypted-command-line-diary-with-python/) 这篇精彩的文章，演示并讲解了如何使用 SQLite, SQLCipher 及 Peewee 来创建一个包含目录、日记及其它内容的加密文件。

* 通过 [官方的 Peewee 快速入门文档](http://docs.peewee-orm.com/en/latest/peewee/quickstart.html) 及这个 [Twitter 克隆示例应用](http://docs.peewee-orm.com/en/latest/peewee/example.html)，你会学到创建 Peewee 项目所需的各方面知识。

* [Django ORM 的短板及对 Peewee 的审视](http://charlesleifer.com/blog/shortcomings-in-the-django-orm-and-a-look-at-peewee-a-lightweight-alternative/) 这篇来自 Peewee ORM 作者的文章，讲解了 Peewee 中的一些设计决策，是如何应对 Django ORM 的相应实践短板的。

* [如何只用一小时或更少时间用 Flask 创建一个博客系统](http://charlesleifer.com/blog/how-to-make-a-flask-blog-in-one-hour-or-less/) 这篇教程写得相当不错，里面的博客系统后端使用了 [Peewee ORM](https://peewee.readthedocs.org/en/latest/) 来代替 SQLAlchemy。


### Pony ORM 相关资源
* [为什么说你应该尝试下 Pony ORM](http://jakeaustwick.me/why-you-should-give-ponyorm-a-chance/) 讲解了 Pony ORM 的一些优点，这些特性使得 Pony ORM 值得一试。

* [Pony ORM 简介](http://www.blog.pythonlibrary.org/2014/07/21/python-101-an-intro-to-pony-orm/) 讲解了该库的基本用法，例如创建数据库和处理数据等。

* Pony ORM 的作者在 Stack Overflow 上对 [Pony ORM 是如何运作的](http://stackoverflow.com/questions/16115713/how-pony-orm-does-its-tricks) 的解答，无论你是否使用该 ORM，还是只想找出这些优秀代码的工作原理，都值得一读。

### SQLObject 相关资源
* 这篇关于 [使用 SQLObject 进行对象-关系映射](http://www.andypatterns.com/index.php/blog/object_relational_mapping_pattern_-_using_sqlobj/) 的文章对 ORM 背后的相关概念进行了讲解，并且展示了如何使用的相关 Python 代码。

* Ian Bicking 早在 2004 年就发表了关于 SQLObject 的一次演讲： [SQLObject 及 Python 的数据库编程](http://www.ianbicking.org/docs/sqlobject-presentation/sqlobject-and-database-programming.html)。
