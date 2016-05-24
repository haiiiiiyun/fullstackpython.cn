title: Python 2 还是 3？
category: page
slug: python-2-or-3
sortorder: 0104
toc: False
sidebartitle: Python 2 还是 3？
meta: 了解你到底应该用 Python 2 还是 Python 3 来编写应用。
translators: haiiiiiyun.github.io
updated: 2016-05-24 14:12

# Python 2 还是 3？

Python 编程语言目前正处在从版本 2 升级到版本 3 的漫长过渡期中。初学者通常会有他们到底应该学习哪个版本的问题。听到 Python 3 最初是在 2008 年发布的，但目前仍不是作为默认版本安装在很多操作系统上，这令人困惑。

告诉你个好消息： 无论你从哪个版本开始学起都不会有问题的。尽管这两个版本在 unicode 处理和语法上有些许不同，但对于其它大部分来说，你先学的 Python 2 然后再学 Python 3 不会又要从头学起。

我个人推荐初学者现在应该从 Python 3 开始学起。因为现在已经能找到足够多的 [好资料](/best-python-resources.html) 来指导我们从零基础开始学习 Python 3。

However, if you are interested in DevOps-type work with 
[configuration management tools](/configuration-management.html) such as 
Ansible or Fabric, then you'll have to stick to Python 2 because they have
yet to upgrade to support Python 3. If you know there are libraries you must
use in a project, check the 
[Python Walls of Superpowers](https://python3wos.appspot.com/). If you're
using Django, there is also a wall specifically for 
[Python 3 compatibility of popular Django packages](http://djangowos.com/).


### Python 2 to 3 resources
* Want to know all of the advantages and what's changed in Python 3 
  compared to Python 2? There's 
  [an official guide to Python 3 changes](https://docs.python.org/3/whatsnew/index.html)
  you'll want to read.

* The official 
  [porting code to Python 3](https://wiki.python.org/moin/PortingToPy3k/)
  page links to resources on porting Python code as well as underlying C
  implementations. There is also a 
  [quick reference for writting code with Python 2 and 3 compatibility](https://wiki.python.org/moin/PortingToPy3k/BilingualQuickRef).

* [Python 3 in 2016](https://hynek.me/articles/python3-2016/) explains
  that many newer Python developers have only used Python 3 and as that
  cohort continues to grow it will have an outsized impact on further
  adoption.

* [Python 3 is winning](https://blogs.msdn.microsoft.com/pythonengineering/2016/03/08/python-3-is-winning/)
  presents data and graphs from PyPI to show that at the current rate,
  by mid-2016 overall Python 3 library support will overtake Python 2 
  support.

* [The stages of the Python 3 transition](http://www.snarky.ca/the-stages-of-the-python-3-transition)
  provides perspective from a core Python developer on how the transition from
  Python 2 to 3 is going as of the end of 2015.

* [Porting to Python 3 is like eating your vegetables](http://nothingbutsnark.svbtle.com/porting-to-python-3-is-like-eating-your-vegetables)
  explains that there are treats in Python 3 that are worth porting for and
  has some tips on making the transition easier.

* [Moving from Python 2 to Python 3](http://ptgmedia.pearsoncmg.com/imprint_downloads/informit/promotions/python/python2python3.pdf)
  is a PDF cheatsheet for porting your Python code.

* [Django and Python 3 How to Setup pyenv for Multiple Pythons](https://godjango.com/96-django-and-python-3-how-to-setup-pyenv-for-multiple-pythons/)
  is a screencast showing how to run both Python 2 and 3 for different
  projects using pyenv.

* [Scrapy on the road to Python 3 support](http://blog.scrapinghub.com/2015/08/19/scrapy-on-the-road-to-python-3-support/)
  explains from the perspective of a widely used Python project what their
  plan is for supporting Python 3 and why it has taken so long to make it 
  happen.

* [Python 3 Readiness](http://py3readiness.org/) is a visualization of
  which most popular 360 libraries (by downloads) are ready to be
  used with Python 3.

