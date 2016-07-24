title: SQLite
category: page
slug: sqlite
sortorder: 0507
toc: False
sidebartitle: SQLite
meta: SQLite 是一款内置于 Python 标准库的关系型数据库，它使用单个文件存储数据。
authors: haiiiiiyun.github.io
writing-time: 2016-07-24 12:03--12:38


# SQLite
SQLite 是一款开源的关系型数据库，它自 Python 2.5 开始就已包含于 Python 标准库中。pysqlite 这个数据库驱动器也已包含在了标准库中，因此在 Python 应用中访问一个 SQLite 数据库不再需要任何的外部依赖包。

<img src="/img/sqlite.jpg" width="100%" alt="SQLite logo." class="technical-diagram" />

<div class="well see-also">SQLite 是对 <a href="/databases.html">关系型数据库</a> 概念的一种实现。 在 <a href="/data.html">数据</a> 那一章学习更多相关知识，或者到 <a href="/table-of-contents.html"> 总目录页</a> 了解所有主题。</div>


### SQLite 相关资源
* [sqlite3 - 嵌入式关系型数据库](https://pymotw.com/2/sqlite3/) 是一篇内容丰富的教程，展示了创建、读取、更新和删除等开发者在使用 SQLite 过程中经常会用到的一些操作。

* [一份简单的按步 SQLite 教程](http://www.blog.pythonlibrary.org/2012/07/18/python-a-simple-step-by-step-sqlite-tutorial/) 演示了如何创建数据库，以及如何插入、更新、查询和删除数据等操作。

* [SQLite: 保持简单的艺术](http://www.jarchitect.com/Blog/?p=2392) 通过 SQLite 代码库中的 C 示例代码，向我们展示了为何经过了 15+ 年的活跃开发后，它的设计还能保护如此地一致和紧凑。 [在 SQLite 网站上还有一篇非常好的设计文档](http://sqlite.org/src4/doc/trunk/www/design.wiki)，讲解了它的很多设计准则。

* [我的 SQLite 资源列表](http://charlesleifer.com/blog/my-list-of-python-and-sqlite-resources/) 是一份有关 SQLite 的有用工具及学习该数据库的相关教程的资源列表。

* [用 Python 扩展 SQLite](http://charlesleifer.com/blog/extending-sqlite-with-python/) 使用 Peewee 这个 [对象-关系 映射器 (ORM)](/object-relational-mappers-orms.html) 来实现虚拟表并且在 SQLite 之后进行了数据聚合。

* [在 Flask 中使用 SQLite](http://flask.pocoo.org/docs/0.10/patterns/sqlite3/) 讲解了如果在 Flask 中抛开 ORM 而直接查询 SQLite 数据库。

* [SQLite 浏览器](http://sqlitebrowser.org/) 是 SQLite 的一款开源图形界面软件。

* [Python 标准库官方文档中的 sqlite3 模块页](https://docs.python.org/3/library/sqlite3.html) 包含了大量有关如何在 Python 应用中使用该数据库的情景代码示例。

* [在 Python 中使用 SQLite JSON1 和 FTS5 扩展](http://charlesleifer.com/blog/using-the-sqlite-json1-and-fts5-extensions-with-python/) 展示了如何将 json1 和 fts5 (全文检索) 编译到 SQLite 3.9.0+ 中以及如何使用这些新特性。

* [深入研究 SQLite](http://blog.regehr.org/archives/1292) 该文的作者在对 SQLite 源码进行研究时，对其内部机理进行了深入分析，并展示了发现的一些 Bug （然后修复）。
