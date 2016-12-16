title: 数据库
category: page
slug: databases
sortorder: 0502
toc: False
sidebartitle: 关系型数据库
meta: 关系型数据库在很多 Python 应用的数据存储中起来了至关重要的作用。
updated: 2016-07-09 20:34--23:28


# 数据库
数据库是建立在操作系统的文件系统之上的一种抽象，它使得对持久性数据的创建、读取、更新和删除等的操作变得更加容易。

## 为什么说数据库很有必要？
Web 应用在更高的层次上存储数据并以更有用的方式将数据呈现给用户。例如，Google 存储道路相关的数据，但它通过 [地图](https://www.google.com/maps/) 应用可向我们提供从一个地点到另一个地点的驾驶向导。因为数据是按结构化方式存储的，因此提供驾驶向导是可能的。

数据库使得结构化存储变得即可靠又快速。它们还提供了一种数据应该如何被保存和提取的认知模型，因而你无需在每次创建新应用时都要指出如何处理数据。

<div class="well see-also">对数据库这个概念的实现有很多种，包括 <a href="/postgresql.html">PostgreSQL</a>、 <a href="/mysql.html">MySQL</a> 和 <a href="/sqlite.html">SQLite</a> 等。 还存在被称为 <a href="/no-sql-datastore.html">NoSQL 数据存储</a> 的非关系型数据库。到 <a href="/data.html">数据</a> 这一章学习更多的相关知识，或者到 <a href="/table-of-contents.html">总目录页</a> 去查看全部主题。</div>


## 关系型数据库
Python Web 应用中用得最多的数据存储抽象是一组关系型数据表。另外的存储抽象会在 [NoSQL](/no-sql-datastore.html) 页讲解。

关系型数据库将数据存储在一系列的数据表中。数据表之间的互连关系通过 *外键* 指定。外键是从一个关系型数据表的一行指向某表的另一行的一个唯一引用，被指向的某表可以和指向的表相同，但是通常是不同的表。

数据库存储的实现在复杂度上各有不同。SQLite，是一种包含在 Python 中的数据库系统，它为每个数据库创建一个单独的文件来存放数据。其它的数据库系统，如 [PostgreSQL](/postgresql.html)、 [MySQL](/mysql.html)、 Oracle 和 Microsoft SQL Server 都具有更加复杂的持久化方案，并且提供对 Web 应用很有用的额外高级功能。这些高级功能包括但不限于：

1. 一个主数据库和一个或多个只读从数据库实例之间的数据复制功能
1. 能高效存储如 JavaScript 对象标记 (JSON) 等半结构化数据的高级列类型
1. 允许在多个数据库间进行水平扩展的数据分片，分片以数据一致性的延迟为代价，使得每个分片都能作为一个可读写的实例使用。
1. 监测、分析及能提供数据库模式和表的其它有用的运行时信息的功能。

通常， Web 应用开始时只使用一个数据库实例，比如用只有一个直接模式的 PostgreSQL。随着时间的推移，数据库模式演变成了使用模式迁移的更加复杂的结构，而像复制、分片、监测等高级功能，随着应用用户的需求及数据库使用的增加，也变得越来越有用。


## Python Web 应用最常用的数据库
[PostgreSQL](http://www.postgresql.org/) 和 [MySQL](http://www.mysql.com/) 是用于存储 Python Web 应用数据的两个最常用的开源数据库。

[SQLite](http://www.sqlite.org/) 是一种将数据存储在存储器的单个文件上的数据库。 SQLite 内置在 Python 中，但是每次允许一个连接对它进行存取。因此强烈建议不要 [在 Web 应用的生产环境中使用 SQLite](https://docs.djangoproject.com/en/dev/ref/databases/#database-is-locked-errors)。


## PostgreSQL
PostgreSQL 是被推荐在 Python Web 应用中使用的一种关系型数据库。它的功能集、活跃的开发及稳定性使得当今数以百万计的 Web 应用都将它作为后端使用。

在 [PostgreSQL 页](/postgresql.html) 上了解更多关于在 Python 中使用 PostgreSQL 的知识。


## MySQL
MySQL 是能在 Python 应用中使用的另一种可靠的开源数据库实现。MySQL 相比 PostgreSQL 更易入门，但是它没有 PostgreSQL 功能丰富。

到专门的 [MySQL 页](/mysql.html) 上了解有关在 Python 应用中使用 MySQL 的知识。


## 用 Python 连接数据库
要通过 Python 来处理关系型数据库，你需要使用代码库。 连接关系型数据库的最常用库是：

* 连接 PostgreSQL 的 [psycopg2](http://initd.org/psycopg/)

* 连接 MySQL 的 [MySQLdb](https://pypi.python.org/pypi/MySQL-python/1.2.5)

* 连接 Oracle 的 [cx\_Oracle](http://cx-oracle.sourceforge.net/)

对 SQLite 的支持已内置于 Python 2.7+ 中，因此不需要另外的库。只需 "import sqlite3" 就能开始与这个基于单文件的数据库进行交互了。


## 对象-关系 映射
对象-关系 映射器 (ORM) 使得开发人员无需写 SQL 查询语句，而只需编写 Python 代码就能从后端存取数据。每个 Web 应用框架对 ORM 的集成处理都有所不同。有 [一整页是专门讲述对象-关系 映射](/object-relational-mappers-orms.html) (ORM) 的，你应该可以通过它来了解这个主题知识。


## 数据库第三方服务
许多公司运营着可扩展的数据库服务器来提供托管服务。托管的数据库，根据提供商的不同，通常能提供自动化的备份和恢复，强化了的安全配置和方便的垂直扩展等功能。

* [Amazon 关系型数据库服务 (RDS)](http://aws.amazon.com/rds/) 提供预配置的 MySQL 和 PostgreSQL 实例。根据存储和性能的需求，这些实例可以按需扩大或缩小配置。

* [Google 云 SQL](https://developers.google.com/cloud-sql/) 服务提供受控的、可备份、可复制和自动进行补丁更新的 MySQL 实例。云 SQL 与 Google App Engine 集成在一起，但是也可以单独使用。

* [BitCan](http://www.gobitcan.com/) 同时提供 MySQL 和 MongoDB 托管服务器，并具有可扩展的备份服务。

* [ElephantSQL](https://www.elephantsql.com/) 是一家 “服务即服务” 的公司，它托管 PostgreSQL 数据库，并且基于 Amazon Web 服务实例对服务器的配置、备份和数据连接进行处理。


## 通用数据库相关资源
* [关系型数据库是如何运作的？](http://coding-geek.com/how-databases-work/) 这篇长文详细讲述了排序、查询、合并及其它我们使用像 PostgreSQL 等已连接的关系型数据库时常常熟视无睹的这些操作。

* [我为什么喜欢数据库](https://medium.com/@jeeyoungk/why-i-love-databases-1d4cc433685f) 是一篇非常精彩的文章，讲述了 CAP 原理（CAP Theorem）、分布式系统以及有关数据库理论和实现的核心知识的其它主题。

* [编写更好的 SQL 代码](http://www.craigkerstiens.com/2016/01/08/writing-better-sql/) 这篇简短的代码风格指南能教你编写出更加易读的查询语句。

* [数据库引擎](http://db-engines.com/en/ranking) 对最流行的数据库管理系统进行了排序。

* [数据库周刊](http://dbweekly.com/) 是一份关于通用数据库的文章和资源的每周集锦。

* [数据库集成测试策略](https://julien.danjou.info/blog/2014/db-integration-testing-strategies-python) 讲述的这个不一样的主题，在每一个现实项目中都会碰到。

* [异步 Python 和数据库](http://techspot.zzzeek.org/2015/02/15/asynchronous-python-and-databases/) 这篇文章就阻塞与异步事件模型的差异，导致许多 Python 数据库驱动不进行修改不能使用这个问题进行了深入的讲解。假如你想通过 Tornado 或 gevent 使用 [WebSockets](/websockets.html) 的话，绝对值得一读。

* [PostgreSQL vs. MS SQL 服务器](http://www.pg-versus-ms.com/) 以一个数据分析师的视角对这两个数据库服务器之间的区别进行了说明。


## 数据库学习清单
1. 在你的服务器上安装 PostgreSQL。假设你在 Ubuntu 上使用以下命令安装：
   ``sudo apt-get install postgresql``。

1. 确保 [psycopg2](http://initd.org/psycopg/) 库在你的应用的依赖文件中。

1. 配置你的 Web 应用，使其连接到这个 PostgreSQL 实例。

1. 可以通过 Django [内置的 ORM](https://docs.djangoproject.com/en/dev/topics/db/) 或者 [Flask 的 SQLAlchemy](http://www.sqlalchemy.org/)，在你的 ORM 中创建数据模型。

1. 创建数据库表，或者如果使用了 ORM 的话，将你的 ORM 模型与 PostgreSQL 实例进行同步。

1. 通过你的 Web 应用，开始在数据库中创建、读取、更新和删除数据。
