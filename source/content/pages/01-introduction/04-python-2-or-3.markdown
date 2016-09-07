title: Python 2 还是 3？
category: page
slug: python-2-or-3
sortorder: 0104
toc: False
sidebartitle: Python 2 还是 3？
meta: 学习关于你到底应该用 Python 2 还是 Python 3 来编写应用的知识。
translators: haiiiiiyun.github.io
updated: 2016-05-24 14:12

# Python 2 还是 3？

Python 编程语言目前正处在从版本 2 升级到版本 3 的漫长过渡期中。初学者通常会有到底该学哪个版本的问题。Python 3 最初是在 2008 年发布的，但目前仍不是作为默认版本安装在很多操作系统上，听到这些很令人困惑。

告诉你个好消息： 无论你从哪个版本开始学起都不会有问题的。尽管这两个版本在 unicode 处理和语法上有些许不同，但对于其它大部分来说，你先学的 Python 2 然后再学 Python 3 不会又要从头学起。

我个人推荐初学者现在应该从 Python 3 开始学起。因为现在已经能找到足够多的 [资料](/best-python-resources.html) 来指导我们从零基础开始学习 Python 3。

但是，如果你对 [DevOps](http://baike.baidu.com/view/5705743.htm) 型工作感兴趣，并且使用像 Ansible 或 Fabric 等 [配置管理工具](/configuration-management.html)，那么你还是应该用 Python 2，因为这些工具还不支持 Python 3。如果你知道项目中必须要用到某些库，先在 [Python 超能墙](https://python3wos.appspot.com/) 网站上查下兼容性。如果你用 Django 的话，也有个类似的网站叫 [常用 Django 包的 Python 3 兼容性](http://djangowos.com/)。


### 从 Python 2 转到 3 的相关资源
* 想知道 Python 3 与 Python 2 相比都有什么改动以及 Python 3 的所有优势吗？你需要看下 [Python 3 修改情况的官方文档](https://docs.python.org/3/whatsnew/index.html)。

* 在官方的 [将代码移植到 Python 3](https://wiki.python.org/moin/PortingToPy3k/)页面上列出了如何移植 Python 代码及底层的 C 代码等相关资源链接。 还有一个网站叫 [编写与 Python 2 和 3 兼容的代码之快速参考](https://wiki.python.org/moin/PortingToPy3k/BilingualQuickRef)。

* [2016 年的 Python 3](https://hynek.me/articles/python3-2016/) 上陈述了现在很多 Python 开发新手只使用 Python 3， 如果这个队伍继续壮大，将会对以后 Python 3 的采用产生特别大的影响。

* [Python 3 是赢家](https://blogs.msdn.microsoft.com/pythonengineering/2016/03/08/python-3-is-winning/) 上的数据和图表来自 PyPI，可以看出如果以当前速度发展，到 2016 年中期，支持 Python 3的库总量将超过 支持 Python 2 的库。

* [Python 3 过渡期的各阶段](http://www.snarky.ca/the-stages-of-the-python-3-transition) 从一个 Python 核心开发人员的角度，阐述了截止 2015 年底 Python 2 怎样过渡到 Python 3 的过程。

* [移植到 Python 3 就像要求你吃完蔬菜](http://nothingbutsnark.svbtle.com/porting-to-python-3-is-like-eating-your-vegetables)， 阐述了 Python 3 有些特性值得我们将代码移植过去，同时还提供了一些怎样移植更省力的小建议。

* [从 Python 2 移植到 Python 3](http://ptgmedia.pearsoncmg.com/imprint_downloads/informit/promotions/python/python2python3.pdf) 是一份如何移植 Python 代码的 PDF 小抄。

* [Django 和 Python 3 如何设置 pyenv 来支持多个 Python 版本](https://godjango.com/96-django-and-python-3-how-to-setup-pyenv-for-multiple-pythons/)， 是一部讲述如何用 pyenv 来实现同时运行 Python 2 和 3，以支持不同的项目。

* [Scrapy 的 Python 3 支持之路](http://blog.scrapinghub.com/2015/08/19/scrapy-on-the-road-to-python-3-support/)，以一个广为使用的 Python 项目的角度阐述了它的 Python 3 支持计划，以及为何实施起来花了这么长时间的原因。

* [Python 3 准备就绪](http://py3readiness.org/) 是一个有关 360 个最受欢迎的 Python 库（基于下载量）是否已支持 Python 3 的可视化页面。

* 所有主要的科研型 Python 类库都承诺不晚于 2020 年，即当 Python 2 维护期结束时，[放弃支持 Python 2](https://python3statement.github.io/)。该承诺通过公开声明它们的意图来大力鼓励对 Python 3 的采纳。
