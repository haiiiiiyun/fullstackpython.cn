title: 应用程序依赖
category: page
slug: application-dependencies
sortorder: 0709
toc: False
sidebartitle: 应用程序依赖
meta: Python web 应用依赖于许多代码库。快来 Full Stack Python 学习更多有关应用程序依赖的知识吧。
translators: blog.chriscabin.com
updated: 2016-07-18 15:00

# 应用程序依赖
应用程序依赖是指除了你的项目代码外，其它用于创建和运行你的应用所必须的库。

## 为何应用程序依赖很重要？
Python web 应用程序是建立在由无数开源程序员已经完成的工作基础上的。应用程序依赖包括但不限于 web 框架，还有很多用于抓取、解析、处理、分析、可视化以及其它库。Python 的生态环境对于发现、检索和安装依赖库很有帮助，从而使得开发者可以更加轻松地创建应用。

## 查找库
Python 的包都被存储在为人熟知的 [Python 包索引](https://pypi.python.org/pypi)（PyPI）上。PyPI 包含了搜索的功能，它可以根据关键词条目返回根据使用频度和相关性排序的结果。

除了 PyPI，还有无数的资源中列出了常用的或者“必备”的库。当然，最终使用什么样的应用程序依赖库还是取决于你自己以及你想要构建的功能。然而，浏览一下这些库的列表还是非常有帮助的，万一你会发现一个可以用于解决问题的库呢。这样你就可以复用别人的代码而不是自己完全重写。一些最好的 Python 库合集如下：

* [Python.org 上有用的模块](https://wiki.python.org/moin/UsefulModules)
  它给模块按照目录进行分组。

* [GitHub 上探索流行的仓库](https://github.com/trending?l=python)
  展示了 GitHub 上最近一天、一周和一个月流行的 Python 开源项目。

* 这有个列表： [20 个你必须拥有的 Python 库](http://freepythontips.wordpress.com/2013/07/30/20-python-libraries-you-cant-live-without/)
  ，它是一个包含了从数据分析到测试工具的大范围的库合集。

* 事实上，维基百科也有一个扩展的 [页面专门讲解了 Python 库](http://en.wikipedia.org/wiki/List_of_Python_software) ，并且是按照目录分组的。
  

## 隔离依赖
将依赖与系统级别的包分开安装的，可以防止库版本冲突的问题发生。最常见的隔离手段是采用虚拟环境 [virtualenv](https://virtualenv.pypa.io/en/latest/)。每个虚拟环境（virtualenv）都有一个独立的 Python 解释器以及来自 site-packages 目录的依赖库的副本。为了使用虚拟环境（virtualenv），你必须首先使用 virtualenv 命令创建并激活虚拟环境。

Virtualenv 会在隔离的环境下存储依赖库。然后，web 应用就会依靠创建的那个含有独立的 Python 解释器副本和来自 site-packages 目录拷贝的虚拟环境来运行。下面的这幅图片可以从更高层次看一个配有 virtualenv 的服务器是怎样工作的。

<img src="/img/server-setup.png" alt="How the virtualenv separates dependencies on the server." width="100%" class="technical-diagram" />


## 安装 Python 依赖
当一个虚拟环境（virtualenv）激活后，安装 Python 库依赖的推荐方法就是使用 [pip](http://www.pip-installer.org/en/latest/) 命令。

Pip 和 virtualenv 工作在一起，并且责任互补。Pip 负责从 [PyPi](https://pypi.python.org/pypi) 中心仓库下载并安装应用依赖。

## requirements.txt
Pip 的使用惯例是，可以使用一个`requirements.txt`文件指定应用程序依赖。当你构建一个 web 应用时，你应当在项目的主目录下包含一个`requirements.txt`文件。

Python web 应用的项目依赖库应当指定相应的版本号，如下：

    django==1.6
    bpython==0.12
    django-braces==0.2.1
    django-model-utils==1.1.0
    logutils==0.3.3
    South==0.7.6
    requests==1.2.0
    stripe==1.9.1
    dj-database-url==0.2.1
    django-oauth2-provider==0.2.4
    djangorestframework==2.3.1

带有精确版本号或者 Git 标签的依赖是非常重要的，因为如果不那样的话，将会使用最新版本的依赖库。虽说保持更新听起来不错，但是实际上，你没法保证你的应用可以在所有的依赖都使用最新版本后还能继续工作。开发者们对升级应当慎重，并且要通过测试确保新版的依赖库没有向后兼容方面的修改。

## setup.py
还有一种指定 Python 库和依赖的方式，就是使用 [setup.py](http://stackoverflow.com/questions/1471994/what-is-setup-py) 。
Setup.py 是发布并安装 Python 库的标准方法。如果你正在构建一个 Python 库，如
[requests](http://www.python-requests.org/en/latest/) 或者 [underwear](https://github.com/makaimc/underwear)，你就必须要包含一个 setup.py 脚本，这样依赖管理器就可以正确地安装应用库及其依赖。在 Python 社区，仍然有一些关于 requirements.txt 和 setup.py 的区别的疑惑，所以请阅读这篇
[不错的文章](https://caremad.io/2013/07/setup-vs-requirement/) 来了解更多内容。


## 应用程序依赖相关的资源
* [Jon Chu](https://twitter.com/jonathanchu) 写的
  [virtualenv 和 pip 基础](http://jonathanchu.is/posts/virtualenv-and-pip-basics/) 是非常不错的介绍。

* [关于 virtualenv 和 pip 的介绍](http://dabapps.com/blog/introduction-to-pip-and-virtualenv-python/) 
  分析了这些工具可以解决什么问题以及如何使用它们。

* [现代 Python 黑客工具](http://www.clemesha.org/blog/modern-python-hacker-tools-virtualenv-fabric-pip/) 
  包括了针对 virtualenv、Fabric 和 pip 非常详细的说明。
  
* 有时候，会产生究竟该使用 Python 的依赖管理器，还是该使用一个 Linux 依赖管理器的争论。 这篇文章给出了 [一个有关那个争论的观点](http://notes.pault.ag/debian-python/)。

* [Open source trust scaling](http://lucumr.pocoo.org/2016/3/24/open-source-trust-scaling/)
  是一篇针对 Python 社区（和其他社区）的好文章，它是基于另一篇文章
  [left-pad NPM 的情况](https://medium.com/@azerbike/i-ve-just-liberated-my-modules-9045c06be67c)，那篇文章作者撤出了许多位于 Node.JS 社区的依赖包。

* 这个在 Stack Overflow 上的问题详细地说明了如何
  [为 Python 应用开发设置虚拟环境](http://askubuntu.com/questions/244641/how-to-set-up-and-use-a-virtual-python-environment-in-ubuntu)。

* 还有一个在 Stack Overflow 上的页面回答了
  [在使用虚拟环境时如何设置环境变量](http://stackoverflow.com/questions/9554087/setting-an-environment-variable-in-virtualenv)。

* [使用 pip + virtualenv + virtualenvwrapper 的小贴士](http://mrcoles.com/tips-using-pip-virtualenv-virtualenvwrapper/)
  展示了在使用这些工具时如何通过 shell 别名和 postactivate virtualenvwrapper 钩子函数来改善使用体验。

* 和之前的版本相比，pip 7 主要在速度上有了改进。参阅
  [这篇文章来了解有哪些不同之处](https://lincolnloop.com/blog/fast-immutable-python-deployments/)
  ，还有，记得一定要升级。

* [如何向 PyPI 提交包](http://peterdowns.com/posts/first-time-with-pypi.html)
  是一个简单明了的介绍，它会快速地帮助你在 PyPI 上获得你的第一个 Python 包。


##开源应用依赖项目
* [Autoenv](https://github.com/kennethreitz/autoenv) 是一个小工具，用激活位于你的项目主目录下的 `.env` 文件中存储的环境变量。virtualenv 并不会管理环境变量，虽然 virtualenvwrapper 提供了处理它们的钩子函数，但通常在开发环境中设置它们的最简单方法就是使用 shell 脚本或者 `.env` 文件。

* [Pipreqs](https://github.com/bndr/pipreqs) 会根据导入自动在一个项目中搜索依赖。然后，它会基于运行这些依赖所必须的库生成一个 `requirements.txt` 文件。需要注意的是，虽然在一个遗留项目使用它很方便，但是它并不会在输出中生成那些库的具体版本号。


## 应用程序依赖学习清单
1. 确保你的 web 应用所需要的依赖库都包含在一个 requirement.txt 文件中，并且指定了版本号。

1. 获取最近安装的依赖库最简单的方法就是使用 `pip freeze` 命令。

1. 创建一个新的虚拟环境（virtualenv），然后使用命令 `pip install -r requirements.txt` 从你的  `requirements.txt` 文件中安装依赖。

1. 检查你的应用程序在新的虚拟环境（virtualenv）中能否正常工作，并且是否只是安装了来自  `requirements.txt` 文件中列出的依赖。
