title: MySQL
category: page
slug: mysql
sortorder: 0506
toc: False
sidebartitle: MySQL
meta: MySQL 是一款开源的数据库系统，它通常被 Python 开发人员用于存取数据。
authors: haiiiiiyun.github.io
writing-time: 2016-07-24 09:53--11:55


# MySQL
MySQL 是 [关系型数据库](/databases.html) 的一种开源实现，它用于存取数据。

<img src="/img/mysql.png" width="100%" alt="MySQL logo." class="technical-diagram" />


## MySQL 还是 PostgreSQL？
MySQL 是一款可运用于 Python Web 应用的开源数据库实现。MySQL 相比 [PostgreSQL](/postgresql.html) 更易入门。但是，Python Web 开发人员通常更偏爱 PostgreSQL 的设计，特别在随着应用程序的演进需要进行数据迁移的时候。

<div class="well see-also">MySQL 是对 <a href="/databases.html">关系型数据库</a> 概念的一种实现。 在 <a href="/data.html">数据</a> 那一章学习更多相关知识，或者到 <a href="/table-of-contents.html"> 总目录页</a> 了解所有主题。</div>


## MySQL 的 Python 驱动器
在 Python 应用中访问 MySQL 需要一个数据库驱动器（也叫作 “连接器”）。当然驱动器可以作为应用的一部分进行编写，但是实践中多数开发人员会采用一个现成的开源驱动器。

随着 Python 3 的引入，MySQL 驱动器出现了一个大问题。 [MySQLdb](https://pypi.python.org/pypi/MySQL-python/1.2.5) 是最流行的库之一，但是它现在无法与 Python 3 兼容，并且还没有更新计划。于是出现了 MySQLdb 的一个分支，叫 [mysqlclient](https://pypi.python.org/pypi/mysqlclient)，它增加了对 Python 3 的兼容性。

mysqlclient 分支很不错，因此当前的 MySQLdb 用户在升级到 Python 3 后，在现有项目中只需用 mysqlclient 代替即可。但是，当查找该用哪个 Python 驱动器连接 MySQL 时，该分支经常会造成些许困惑。PostgreSQL 社区对 Python 驱动提供了更好的支持，因此很多开发者决定选用 [PostgreSQL](/postgresql.html)。

抛开驱动器的支持问题，当然完全可以在 Python 3 Web 应用中选用 MySQL 作为后端。这里是一份驱动器列表，并附有对 Python 2、3 或两者的支持度的说明。

* [mysqlclient](https://mysqlclient.readthedocs.io/en/latest/) 是一个 MySQLdb 分支，它支持 Python 2 和 3。

* [MySQL 连接器](http://dev.mysql.com/doc/connector-python/en/) 是 Oracle 的 “官方” （Oracle 当前拥有 MySQL）Python连接器。该驱动器支持 Python 2 和 3，但是确保到 [版本指南](http://dev.mysql.com/doc/connector-python/en/) 上了解哪个发行版与哪个 Python 版本兼容。

* [MySQLdb](https://pypi.python.org/pypi/MySQL-python/1.2.5) 支持 Python 2，在大家还没有开始迁移到 Python 3 之前，经常运用于 Python Web 应用程序中。

* [PyMySQL](https://github.com/PyMySQL/PyMySQL) 用纯 Python (没有 C 低层代码）实现，意在成为 MySQLdb 的直接替代品。但是，该驱动器还不支持一些 MySQL API，因此你的应用是否能用该连接器将取决于你使用了哪些接口。


## 哪些组织使用 MySQL？
该数据库已实际部署在了一些高流量的网站上，如 [Twitter](https://blog.twitter.com/2012/mysql-twitter)、 [Facebook](https://www.facebook.com/notes/facebook-engineering/mysql-and-database-engineering-mark-callaghan/10150599729938920) 和 [许多其它大型机构](http://www.mysql.com/customers/)。但是，因开发 MySQL 的公司 [MySQL AB](http://en.wikipedia.org/wiki/MySQL_AB)，已经被 Sun Microsystems (它后来又被 Oracle 收购）收购，像 [Wikipedia](http://www.zdnet.com/wikipedia-moving-from-mysql-to-mariadb-7000008912/) 和 [Google](http://readwrite.com/2013/09/14/google-waves-goodbye-to-mysql-in-favor-of-mariadb) 等都开始不用该数据库了。MySQL 仍然是一个可行的数据库选项，但是我一直推荐还没有学过 MySQL 的 Python 开发人员学习 PostgreSQL。


### 针对 Python 的 MySQL 相关资源
* [Python 3.4.0 和 MySQL 数据库](http://stackoverflow.com/questions/23376103/python-3-4-0-with-mysql-database) 及 [Python 3 和 MySQL](http://stackoverflow.com/questions/4960048/python-3-and-mysql) 就 Python 3 该使用哪个 MySQL 驱动器这个经常被问到的问题提供了相关的背景知识。

* [糟糕的选择: MySQL](http://blog.ionelmc.ro/2014/12/28/terrible-choices-mysql/) 这篇博文讲述了 MySQL 实现中的一些特定缺陷阻碍了其在 Django ORM 中的使用。

* [使用 Python 来图示化 MySQL 数据库中的数据](http://moderndata.plot.ly/graph-data-from-mysql-database-in-python/) 是个很有趣的研究，它用代码来演示了如何从 MySQL 中提取数据并用 Plotly 对其图示化。

* [MySQL Python 教程](http://zetcode.com/db/mysqlpython/) 使用 MySQLdb 驱动器来连接一个 MySQL 服务器实例，并展示了一些插入和查询数据的示例。


### 通用 MySQL 相关资源
* [如何在 Ubuntu 16.04 上安装使用 MySQL](/blog/install-mysql-ubuntu-1604.html) 是一篇关于如果在 Ubuntu Linux 上安装和运行 MySQL 的快速指南。

* [学习 MySQL 数据库的 28 份初学者教程](http://designm.ag/tutorials/28-beginners-tutorials-for-learning-about-mysql-databases/) 整理了各种介绍 MySQL 主题的相关资料。

* 这篇教程展示了如何在 [Ubuntu 上安装 MySQL](http://www.cs.wcupa.edu/rkline/index/mysql-lin.html)。

* [MySQL 基础教程](https://www.digitalocean.com/community/tutorials/a-basic-mysql-tutorial)，虽然标题不是很新颖，但它很好的演示了使用 MySQL 的开始几个步骤，如创建用户和处理数据表等。

* [Pinterest 将他们的很多 MySQL 工具开源了](https://engineering.pinterest.com/blog/open-sourcing-pinterest-mysql-management-tools)，这些工具可以用于管理数据库实例。

* [再见 MySQL & MongoDB, 你好 PostgreSQL](https://www.userlike.com/en/blog/2015/10/09/bye-by-mysql-and-mongodb-guten-tag-postgresql) 详细阐述了为何 Userlike 这个公司将它们的 MySQL 数据库迁移到 PostgreSQL。

* [MySQL 处理数据增长](https://nylas.com/blog/growing-up-with-mysql/) 讲述了一个公司如何扩展它们的 MySQL 数据库来应对自身的快速增长的故事。

* [监测 MySQL 度量信息](https://www.datadoghq.com/blog/monitoring-mysql-performance-metrics/) 是三部曲系列文章的第一篇，其它两篇分别是 [收集度量信息](https://www.datadoghq.com/blog/collecting-mysql-statistics-and-metrics/) 和 [利用 DataDog 工具进行监测和收集](https://www.datadoghq.com/blog/mysql-monitoring-with-datadog/)。该系列文章阐述了你应该从生产环境下的数据库中收集哪些度量信息以及这些度量信息缘何重要。
