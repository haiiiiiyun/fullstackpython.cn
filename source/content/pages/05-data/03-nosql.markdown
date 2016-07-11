title: NoSQL 数据存储
category: page
slug: no-sql-datastore
sortorder: 0503
toc: False
sidebartitle: NoSQL 数据存储
meta: NoSQL 数据存储持久化数据所采取的方式与传统的关系型数据库不同。到 Full Stack Python 上学习更多有关 NoSQL 的知识。
updated: 2016-07-10 11:46
authors: haiiiiiyun.github.io


# NoSQL 数据存储
绝大多数的 Web 系统都采用关系型数据库存储系统来持久化数据。但是还有另外几种不同的存储表示形式。

1. 键值对
1. 面向文档
1. 列簇表
1. 图

这些持久化数据存储表示法通常不是用来完全替代关系型数据库的，而是作为辅助使用的。由于 NoSQL 数据库所采用的低层持久化形式与关系型数据库不同，这通常也导致了不同的性能特性：在某些读/写条件下有更好的表现，而在另外一些条件下则性能欠佳。

## 键值对
键值对型的数据存储系统基于 [哈希映射](http://en.wikipedia.org/wiki/Hash_table) 这个数据结构。


### 键值对数据存储
* [Redis](http://redis.io/) 是一个开源的内存键值对数据存储系统。Redis 经常被称为 ”Web 应用开发的瑞士军刀“。它可用于存储缓存、列队、和会话数据等，在多数案例中，它的存取速度都比传统关系型数据库快。 [Redis-py](https://github.com/andymccurdy/redis-py) 是 Python 用于操作 Redis 的一个健壮的客户端。

* [Memcached](http://www.memcached.org/) 是另一个广泛使用的内存键值对存储系统。


### 键值对相关资源
* [什么是键值对存储数据库？](http://dba.stackexchange.com/questions/607/what-is-a-key-value-store-database) 这个问题在 Stack Overflow Q&A 上得到了直接地回答。


### Redis 相关资源
* [如何在 Ubuntu 16.04 上通过 Python 3 和 redis-py 使用 Redis](/blog/install-redis-use-python-3-ubuntu-1604.html) 包含了如何安装及在 Python 中起步使用 Redis 的详细步骤。

* "[如何安装和使用 Redis](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-redis)" 这篇教程讲述了如何开始使用这个极其有用的内存数据存储系统。

* [开始使用 Redis 和 Python](http://degizmo.com/2010/03/22/getting-started-redis-and-python/) 演示了如何安装并练习使用 Redis 的基本功能。

* 通过 [Twitter 加大 Redis 规模](https://www.youtube.com/watch?v=rP9EKvWt0zo) 这个视频可以了解大规模部署 Redis 的幕后详情。

* [Walrus](http://charlesleifer.com/blog/walrus-lightweight-python-utilities-for-working-with-redis/) 是针对 Redis 的一个高级 Python 封装库，它加入了缓存、查询和其它的数据结构组件。

* [在 Python 中通过 Asyncio 存取 Redis](http://jamesls.com/writing-redis-in-python-with-asyncio-part-1.html) 以一个详细的例子展示了如何通过 Asyncio 这个 Python 3.4+ 中的新标准库来使用 Redis。

* [如何获取 Redis 度量值](https://www.datadoghq.com/blog/how-to-collect-redis-metrics/) 展示了如何使用 Redis CLI 客户端来获取有关延时的关键度量值。

* [针对 Redis 服务器的渗透测试](http://averagesecurityguy.info/2015/09/17/pentesting-redis-servers/) 阐述了安全问题无论在你的应用中还是你使用的数据库上都是非常重要的。

* Redis，和其它任何的关系型或者 NoSQL 数据库一样，都需要依据 [安全准则](http://www.antirez.com/news/96) 进行安全设置。这有一篇文章讲述了 Redis 的主要作者 [通过攻击 Redis](http://www.antirez.com/news/96) 来展示了 Redis 默认配置在易用性和安全性之间进行的权衡。


## 面向文档
面向文档的数据库为嵌套数据提供半结构化的表示方式。


### 面向文档的数据存储系统
* [MongoDB](http://www.mongodb.org/) 是一个开源的面向文档的数据存储系统，它使用二进制对象表示法 (BSON）存储格式，该格式和 JSON 类似，因此 Web 开发人员都很熟悉。[PyMongo](http://docs.mongodb.org/ecosystem/drivers/python/) 这个客户端在 Python 代码中通常被用于和一个或多个 MongoDB 实例交互。[MongoEngine](http://mongoengine.org/) 是一个针对 MongoDB 的 Python ORM 系统，它基于 PyMongo 开发。

* [Riak](http://basho.com/riak/) 是一个开源的分布式数据存储系统，它注重可用性、容错性和大规模可部署性。

* [Apache CouchDB](http://couchdb.apache.org/) 也是一个开源项目，它的关注点是倡导使用 RESTful 风格的 HTTP 存取方式来处理存储的 JSON 数据。


### 面向文档的数据存储系统相关资源
* [初创公司使用 MongoDB](http://www.optinidus.com/blogs/guide-to-mongodb-for-startups/) 是关于在新兴领域使用非关系型数据库的一篇指南性文章。

* PyMongo 的创造者和维护者总结了他们在创建这个广受使用的 Python MongoDB 驱动时所下的四个错误决定。
    1. [start\_request](http://emptysqua.re/blog/good-idea-at-the-time-pymongo-start-request/)
    1. [use\_greenlets](http://emptysqua.re/blog/it-seemed-like-a-good-idea-at-the-time-pymongo-use-greenlets/)
    1. [copy\_database](http://emptysqua.re/blog/good-idea-at-the-time-pymongo-copy-database/)
    1. [MongoReplicaSetClient](http://emptysqua.re/blog/good-idea-at-the-time-pymongo-mongoreplicasetclient/)

* “和我一起聊 Python” 播客上的 [Python 和 MongoDB](https://talkpython.fm/episodes/show/2/python-and-mongodb) 这期节目对 MongoDB 的 Python 驱动维护者进行了一次精彩的采访。

* [MongoDB 查询不是总能返回全部的匹配文档！](https://engineering.meteor.com/mongodb-queries-dont-always-return-all-matching-documents-654b6594a827) 演示了如何去了解 MongoDB 查询操作的实际工作原理，并阐述了依赖那些你还没有完全理解其运作原理的技术会埋下潜在的意想不到的风险。


## 列蔟表
列蔟表形式的 NoSQL 数据存储系统基于键值对类型。 每个键值对可以被认为是一行，而列蔟则可类比于关系型数据库模型中的一个表。


### 列蔟表数据存储系统
* Apache [HBase](https://hbase.apache.org/)

* Apache [Cassandra](http://cassandra.apache.org/)


## 图
图数据库通过三个方面来表示和存储数据：结点、边和属性。

一个 *结点* 表示一个实体，如一个人或一家公司。

一条 *边* 表示两个实体之间的关系。例如，一条边可以表示人实体结点和公司实体结点之间的雇佣关系。

*属性* 用于表示结点的相关信息。例如，表示一个人的实体可能会有一个性别属性。


### 图数据存储系统
* [Neo4j](http://www.neo4j.org/) 是一个最常用的图数据库，它运行于 Java 虚拟机系统之上。

* [Cayley](https://github.com/google/cayley) 是一个开源的图数据存储系统，它由 Google 发布，并且主要是用 Go 编写的。

* [Titan](http://thinkaurelius.github.io/titan/) 是针对多结点簇而开发的一个分布式图数据库。


### 图数据存储系统相关资源
* [图数据库简介](http://www.slideshare.net/maxdemarzi/introduction-to-graph-databases-12735789) 上的内容涵盖了 NoSQL 数据存储的发展趋势以及图数据库与其它类型的数据存储系统的对比。


## NoSQL 第三方服务
* [MongoHQ](http://www.mongohq.com/home) 提供 MongoDB 服务。 它无论是在标准的 LAMP 堆栈上还是在 Heroku 上都非常容易设置。


## NoSQL 数据存储系统相关资源
* [NoSQL 数据库: 概论](http://www.thoughtworks.com/insights/blog/nosql-databases-overview) 讲解了什么是 NoSQL，相较于关系型系统，数据是如何以不同方式被存储的，以及什么是一致性、可用性和分区容忍性 (CAP) 定律。

* [CAP 定律概述](http://natishalom.typepad.com/nati_shaloms_blog/2010/10/nocap.html) 介绍了所有数据库操作中必须权衡的一些基本限制。

* [什么是 NoSQL 数据库？通过 Python 编写一个来学习](http://jeffknupp.com/blog/2014/09/01/what-is-a-nosql-database-learn-by-writing-one-in-python/) 这篇详细的文章揭开了 NoSQL 数据库低层是如何运作的神秘面纱。

* [CAP 定律系列](http://blog.thislongrun.com/2015/03/the-cap-theorem-series.html) 讲解了与 NoSQL 相关的一些概念，如 ACID 与 CAP 的对比， CP 与 CA 的对比，以及大规模部署环境下的高可用性。

* [NoSQL 周刊](http://www.nosqlweekly.com/) 这份免费的电子邮件时讯聚合了有关非关系型数据存储的文章、教程和视频内容。

* [NoSQL 比较](http://kkovacs.eu/cassandra-vs-mongodb-vs-couchdb-vs-redis) 列出了大量流行的、基于 BigTable的、特殊用途等的数据库系统，并对每个数据库的特性及其最佳用途做了说明。

* MySQL 和 PostgreSQL 等关系型数据库在其最近的版本中都加入了一些特性来模仿 NoSQL 数据存储系统的一些功能。例如，可以查看这篇博客 [将 MySQL 作为一个键值对存储系统使用](http://engineering.wix.com/2015/12/10/scaling-to-100m-mysql-is-a-better-nosql/) 和这篇文章 [在 PostgreSQL 中存储 JSON](https://blog.codeship.com/unleash-the-power-of-storing-json-in-postgres/)。


## NoSQL 数据存储系统学习清单
1. 理解 NoSQL 数据存储系统为什么在某些情况下使用会比关系型数据库更适合。但是通常这些优势只能在大规模的情况下才能显现出来，因此可能不太适用于你的 Web 应用。

1. 将 Redis 整合入你的项目中，相比于较慢的持久化存储系统， 这能提升速度。将会话数据保存在内存中，相比于将数据保存在使用持久化存储器的传统关系型数据库中，通常来说运行会更快。值得注意的是当内存清空后，其中的数据会被删除，因此任何需要持久化保持的数据仍须定期备份到磁盘上。

1. 评估其它的用例，如将临时的日志存储到 MongoDB 等面向文档的数据存储系统中。
