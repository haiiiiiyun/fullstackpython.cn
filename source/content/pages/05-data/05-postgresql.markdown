title: PostgreSQL
category: page
slug: postgresql
sortorder: 0505
toc: False
sidebartitle: PostgreSQL
meta: PostgreSQL 是一款开源的关系型数据库，它常用于 Python 应用中。
authors: haiiiiiyun.github.io
writing-time: 2016-07-19 19:11--2016-07-24 09:08


# PostgreSQL
[PostgreSQL](http://www.postgresql.org/)， 通常写作 "Postgres"，发音为 "Poss-gres"， 是一款开源的 [关系型数据库](/databases.html) 实现，它常在 Python 应用中作为数据存取的后端使用。

<img src="/img/postgresql.jpg" width="100%" alt="PostgreSQL logo." class="technical-diagram" />


## PostgreSQL 如何应用于 Python 开发？
PostgreSQL 是很多 Python 开发人员的默认数据库选项，包括 Django 团队在测试 [Django ORM](/object-relational-mappers-orms.html) 时也选得它。 相比于 MySQL、SQLServer 和 Oracle，人们通常认为 PostgreSQL 具有更多功能且更加稳定。选择以上任何一款数据库都没有错。但是，由于 PostgreSQL 倾向于被较多的 Python 开发人员选用，因而针对该数据库的驱动器和示例代码也会有更好的文档，在典型使用场景中存在 BUG 的几率也会更小。如果你想在 Django 中使用 Oracle，你会发现有关 Oracle 的配置示例代码相比 PostgreSQL 后端的少得多。

<div class="well see-also">PostgreSQL 是对 <a href="/databases.html">关系型数据库</a> 概念的一种实现。在 <a href="/data.html">数据</a> 那一章学习更多相关知识，或者到 <a href="/table-of-contents.html">总目录页</a> 了解所有主题。</div>


## 为什么说 PostgreSQL 是一个不错的数据库选择？
PostgreSQL 的开源许可允许开发人员无需考虑许可费用问题就可操作一个或多个数据库。开源许可运营模式相较于 Oracle 或其它专有数据库，其花费更少，特别是在规模增加到需要复制和分片的时候。另外，由于从独立开发人员和跨国组织等的大量人员使用 PostgreSQL，因而相比于其它的关系型数据库，找到具有 PostgreSQL 经验的开发人员通常容易的多。

PostgreSQL 核心团队还经常发布更新，从而显著提高了数据库的能力。例如， [PostgreSQL 9.4 版本](http://www.postgresql.org/docs/9.4/static/release-9-4.html) 就增加了 [jsonb 类型](http://www.postgresql.org/docs/9.4/static/datatype-json.html)，用来增强对 JavaScript 对象表示 ([JSON](http://www.json.org/)) 的存储能力，从而减少了在一个应用体系中另外再使用一个独立 [NoSQL 数据库](/no-sql-datastore.html) 的需求。


## 在 Python 中连接 PostgreSQL
在 Python 中使用关系型数据库，需要一个数据库驱动器，通常也叫作数据库连接器。连接 PostgreSQL 的最常用驱动库是 [psycopg2](http://initd.org/psycopg/)。在 [PostgreSQL 官网的 wiki 页上有一份有关所有驱动器的列表](https://wiki.postgresql.org/wiki/Python)，其中包括了一些已经不再维护了的库。如果你使用 [asyncio 这个 Python 标准库](https://docs.python.org/3.4/library/asyncio.html) 的话，你还应该了解下 [aiopg](https://github.com/aio-libs/aiopg)，它还封装了 psycopg2 的异步操作功能。

要想在数据表和对象间抽象出对应关系，许多 Python 开发人员会利用 [对象-关系映射器 (ORM)](/object-relational-mappers-orms.html) 来将 PostgreSQL 中的关系型数据转化成可以在 Python 代码中使用的对象。例如，PostgreSQL 提供关系型数据库功能，而 psycopg 是常用的数据库连接器，但很多 ORM 能用于各种不同的 Web 框架，如下图所示。

<img src="/img/postgresql-orm-examples.png" width="100%" alt="各种不同的 Python ORM 如何与 PostgreSQL 和 psycopg2 连接器一起使用的例子。" class="technical-diagram" />

到 [关于 Python ORM 主题的特定页](/object-relational-mappers-orms.html) 了解更多知识。


## PostgreSQL 数据安全性
如果你使用 Linux，那么使用包管理器就能很容易地安装 PostgreSQL。但是，一旦数据库安装运行后，你的责任才刚刚开始。在将其用于生产环境前，确保：

1. 通过 `pg_hba.conf` 文件将访问者限制到 [一份白名单里](http://www.postgresql.org/docs/9.3/static/auth-pg-hba-conf.html)
1. 开启 [复制](https://www.digitalocean.com/community/tutorials/how-to-set-up-master-slave-replication-on-postgresql-on-an-ubuntu-12-04-vps) 到另一个数据库的功能，另一个数据库最好位于另一个地方的不同基础设施之上。
1. 定期执行 [备份并且测试还原过程](http://www.postgresql.org/docs/current/static/backup.html)
1. 确保你的应用已经对 [SQL 注入攻击](https://www.owasp.org/index.php/SQL_Injection) 进行了预防

尽可以邀请有资质的人员进行一次 [PostgreSQL 安全审计](http://security.stackexchange.com/questions/2517/postgresql-security-audit)，以便找出数据库中的最大安全隐患。小型应用和初创公司刚开始通常负担不了一个全职审计员，但是随着应用程序的发展，它将越有可能成为攻击目标。

存储在数据库中的数据是应用的生命力所在。如果你曾经 [不小心删除过一个生产环境中的数据库](https://www.twilio.com/blog/2014/02/introducing-developer-evangelist-matt-makai.html) 或者是 SQL 注入攻击等恶意行为的受害者，你就会明白：只需事先进行诸如备份、复制和安全举措等额外一点儿工作，都能使数据恢复变得更加容易。


## 针对 Python 的 PostgreSQL 相关资源
有很多针对 Django、Flask 及其它 Web 框架的入门教程资料。以下列出的几篇是我读过的最好的。

* [在 Ubuntu 16.04 上进行 Python 3、 psycopg 和 PostgreSQL 配置](/blog/postgresql-python-3-psycopg2-ubuntu-1604.html) 提供了如何在一个刚安装的 Ubuntu 上安装使用 PostgreSQL 和 Python 3 的操作指南。

* 这篇有关 [在 Django 或 Flask 中使用 PostgreSQL](http://killtheyak.com/use-postgresql-with-django-flask/) 的文章是针对这两个框架的非常精彩的入门指南。

* 这篇文章讲解了如何及为何 PostgreSQL 在许多情况下能用来处理 [全文检索](http://blog.lostpropertyhq.com/postgres-full-text-search-is-good-enough/)。如果想进一步研究的话，[这篇文章讲述了一个开发者使用 SQLAlchemy 来实现 PostgreSQL 全文检索](http://blog.garage-coding.com/2015/12/18/postgres-fulltext-search.html)。

* [django-postgres-copy](http://django-postgres-copy.californiacivicdata.org/en/latest/) 这个工具能根据 Django 数据模型将批量数据导入到 PostgreSQL 数据库中。 [对导入批量数据到 PostgreSQL 这个新开源软件的简介](http://www.californiacivicdata.org/2015/07/17/hello-django-postgres-copy/) 是关于如何在我们的项目中使用该工具的介绍性文章。

* [如何提升 Django 和 PostgreSQL 的测试过程](http://nemesisdesign.net/blog/coding/how-to-speed-up-tests-django-postgresql/) 讲述的一些技巧能提升你的模式迁移后端的测试用例的运行速度。

* [Django 使用数据库后端实现全文检索](http://www.machinalis.com/blog/full-text-search-on-django-with-database-back-ends/) 提供了针对 PostgreSQL 和 [MySQL](/mysql.html) 的代码，用来实现将基本的全文检索功能加入到应用中。

* [Records](https://pypi.python.org/pypi/records/) 对 psycopg2 驱动器进行了封装，它使直接 SQL 访问变得更加容易。相较于使用像 SQLAlchemy 这样的 [ORM](/object-relational-mappers-orms.html)，如果你更偏好写 SQL 语句的话，值得一看。

## 通用 PostgreSQL 相关资源
不是专门针对 Python 的 PostgreSQL 教程对于正确处理数据也是相当有帮助的。

* [PostgreSQL: 好的方面](https://russ.garrett.co.uk/talks/postgres-gds/) 是一份很好的概述性幻灯片，阐述了 PostgreSQL 为何是一个不错的关系型数据库。

* [PostgreSQL 周刊](http://postgresweekly.com/) 是一份每周时讯，它的 PostgreSQL 资源来自网络的。

* [PostgreSQL 物理存储简介](http://rachbelaid.com/introduction-to-postgres-physical-storage/) 对 PostgreSQL 文件存于磁盘何处、这些文件如何存储你的数据以及哪些映射对低层数据库结构起重要作用等知识点提供了可靠讲解。这篇文章通俗易懂，非常值得一读。

* Braintree 写了有关他们 [扩展使用 PostgreSQL](https://www.braintreepayments.com/braintrust/scaling-postgresql-at-braintree-four-years-of-evolution) 的经验。 这篇文章深入讲述了 Braintree 数据库使用的演进历程。

* 这篇文章对 [一个 PostgreSQL 连接所需的花费](http://hans.io/blog/2014/02/19/postgresql_connection/index.html) 进行了预估。

* 没有绝对安全的说法，但是 IBM 的这篇文章讲述了 [如何加固一个 PostgreSQL 数据库](http://www.ibm.com/developerworks/library/os-postgresecurity/)。

* [Postgres 处理数据增长](http://instagram-engineering.tumblr.com/post/40781627982/handling-growth-with-postgres-5-tips-from-instagram)，Instagram 的技术团队就如何扩展 PostgreSQL 数据库设计给我们提供了 5 个具体方法。

* [在 Postgres 中插入及使用一条新记录](http://rob.conery.io/2015/02/09/inserting-using-new-record-postgres/) 就许多开发人员用他们所选的 ORM 编写的一些操作语句，提供了等价的 SQL 语句。

* [通过一个 Select 语句来了解 Postgres 内部机理](http://patshaughnessy.net/2014/10/13/following-a-select-statement-through-postgres-internals) 对查询过程涉及的 PostgreSQL 内部机制进行了精彩剖析。

* 如果你刚开始使用 PostgreSQL，这里有一份 [你应该知道如何去完成的 10 个初学者任务](https://eye.raze.mx/10-beginner-postgresql-tasks-you-should-know/)。

* 题目虽然听起来有点浮夸，但也是一份很有用的列表 [你应该使用的 7 个 PostgreSQL 数据迁移技巧](http://engineering.tilt.com/7-postgresql-data-migration-hacks/)。

* [awesome-postgres](https://github.com/dhamaniasad/awesome-postgres) 上列出了专注于 PostgreSQL 的相关代码库、教程和时讯的资源列表。

* 虽然可以使用图形界面来操作 PostgreSQL，但是你最好还是花些时间来 [熟悉下命令行界面](http://phili.pe/posts/postgresql-on-the-command-line/)。

* 数据库备份很重要，因为数据丢失的情况一定会发生。这篇文章讲解了 [如何对托管在 Amazon Web 服务 EC2 实例上的 PostgreSQL 数据进行备份](http://www.n2ws.com/blog/how-to-backup-your-aws-cloud-based-postgresql-database.html)，如果你选择在云服务器上管理数据库的话。

* [如何修复僵死的 PostgreSQL 查询](https://tech.zalando.com/blog/hack-to-terminate-tcp-conn-postgres/) 展示了当你无法中止一些 PostgreSQL 查询语句时所需的一些技巧。

* [PostgreSQL 中的双向复制 (BDR) 是事务型的吗？](http://sdf.org/~riley/blog/2016/01/04/is-bi-directional-replication-bdr-in-postgres-transactional/) 对 BDR 这个相对晦涩的主题进行了探索，并得出最终结论：BDR 和具有最终一致性的数据存储类似，而与只将一致性作为需求的数据存储不同。

* [PostgreSQL-metrics](https://github.com/spotify/postgresql-metrics) 是一个由 Spotify 的工程师开发的工具，它能从一个 PostgreSQL 数据库中抽取并输出度量信息。我们也可以对该工具进行扩展，从而提取出定制的度量信息。

* [在 Postgres 9.5 中创建一个 文档-存储 混合数据库](https://blog.andyet.com/2016/02/04/postgres-9.5-document-store-hybrid/) 讲解了如何存储和查询 JSON 数据，以类似于 [NoSQL 数据存储](/no-sql-datastore.html) 的方式操作。

* [PostgreSQL 索引: 基本原理](http://eftimov.net/postgresql-indexes-first-principles) 详细讲解了什么是索引，其适用情况及如何在 PostgreSQL 中使用。

* 这篇 [关于 Web 应用高可用性的幻灯片](http://thebuild.com/presentations/pgha-fosdem-2016.pdf) 对那些普遍运用于生产环境下的 Web 应用中的各色数据库配置进行了很好的概述。


### PostgreSQL 监测与性能
监测一个或多个 PostgreSQL 实例，然后对它们进行优化是一项罕见技能。如果你想在应用中处理这些问题，下面的一些资源能帮助你入门。

* 这篇 [PostgreSQL 监测指南](http://russ.garrett.co.uk/2015/10/02/postgres-monitoring-cheatsheet/) 对于了解需要监测什么及如何监测十分便捷有用。

* Craig Kerstiens 写了一篇有关 [理解 PostgreSQL 性能](http://www.craigkerstiens.com/2012/10/01/understanding-postgres-performance/) 的详细文章。

* [PostgreSQL 优化实践指南](https://tech.lendinghome.com/practical-guide-to-postgresql-optimizations-d7b9c2ad6a22) 讲述了通过使用缓存大小、恢复配置和共享缓存来提高数据库性能。

* 这篇关于 [PostgreSQL 性能调优](http://www.geekytidbits.com/performance-tuning-postgres/) 的文章，其内容覆盖了如何查找慢速查询、调整索引及修改查询使其运行更快。

* [从 PostgreSQL 中获取性能信息](http://okigiveup.net/what-postgresql-tells-you-about-its-performance/) 讲解了如何收集常用的性能度量值，并提供了获取这些信息需要运行的查询语句。该文还讲述了性能监测及如何分析触发函数。

* [PostgreSQL 监测查询](https://github.com/nilenso/postgresql-monitoring) 是一个有关 SQL 查询的简单的 GitHub 项目，它可运行于一个 PostgreSQL 实例来对其用量、缓存和膨胀进行侦测。
