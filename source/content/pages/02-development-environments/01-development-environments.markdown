title: 开发环境
category: page
slug: development-environments
sortorder: 0201
toc: True
sidebartitle: 2. 开发环境
meta: 程序员在开发环境中编写代码。在 Full Stack Python 上学习开发环境的更多知识。
authors: haiiiiiyun.github.io
updated: 2016-05-31 14:20


# 开发环境
开发环境就是文本编辑器和 Python 解译器的组合。文本编辑器用来输入源代码。而解译器用来执行你写的代码。文本编辑器可以很简单，比如 Windows 系统上的 Notepad，也可以相当复杂，比如 [PyCharm](https://www.jetbrains.com/pycharm/)，它就是一个完整的集成开发环境（IDE）， 并且在当前主流的操作系统上都能运行。

## 为什么需要开发环境？
Python 代码需要经过编写、执行、测试然后才能构建成应用程序。文本编辑器提供输入代码的功能。解译器使得代码能够运行。测试用来检验代码是否按预期运行，而测试工作要么通过手动进行，或者通过单元测试和功能测试进行。

<div class="well see-also">当你在学习开发环境的相关知识时，请务必查看 <a href="/vim.html">Vim</a> 和 <a href="/emacs.html">Emacs</a>。</div>


## 开发环境案例
这是我（Full Stack Python 的作者 [Matt Makai](/about-author.html)） 用于开发我的大部分 Python 应用的开发环境。我有一台安装了 Mac OS X 系统的 Macbook Pro。[Ubuntu 14.04 LTS](/operating-systems.html) 是通过 [Parallels](https://www.parallels.com/) 安装在虚拟机上的。我的代码在 [vim](http://www.vim.org/) 里输入，然后在命令行上由 [Python 2.7.x](https://www.python.org/download/releases/2.7.8/) 解译器执行。我使用 [virtualenv](https://virtualenv.pypa.io/en/stable/) 创建独立的 Python 解译器，每个解译器包含各自独立的 [应用程序依赖包](/application-dependencies.html) 。我使用 [virtualenvwrapper](http://virtualenvwrapper.readthedocs.org/en/latest/) 在各个解译器间进行快速切换。

这是一套常见的设置方案，当然你也能用更简单的方案或者基于云计算的开发环境来写出好代码。

## 开源文本编辑器
* [vim](http://www.vim.org/) 是我选择的编辑器，该编辑器在大多数类 unix 系统都已默认安装。

* [emacs](http://www.gnu.org/software/emacs/) 是另一款在类 unix 上常用的编辑器。

* [Atom](https://atom.io/) 是一款由 [GitHub](https://github.com) 团队创建的开源编辑器。

## 专有（封闭源码） 编辑器
* [Sublime Text](http://www.sublimetext.com/) 版本 2 和 3 （当前还是 beta 版）都是较流行的文本编辑器，通过插件扩展，能够在它上面增加代码补全、代码检查、语法高亮等功能。

* [Komodo](http://komodoide.com/) 是一款跨平台的文本编辑器和 IDE，它支持主流的语言，包括 Python、 Ruby、 JavaScript、 Go 等。


## Python 专用 IDE
* [PyCharm](https://www.jetbrains.com/pycharm/) 是一款基于 [JetBrains](https://www.jetbrains.com/) 平台的 Python 专用 IDE 。它对学生和开源项目提供免费版本。
 
* [Wing IDE](https://wingware.com/) 是一款需要付费的开发环境，它有集成的调试环境和代码补全功能。

* [PyDev](http://pydev.org/) 是 [Eclipse](https://www.eclipse.org/) 上的一个 Python IDE 插件。


## 托管的开发环境服务
在过去的几年中，出现了一些基于云计算的开发环境。当在一台只有浏览器且无法安装软件的机器上学习时，你会觉得这些工具很有用。它们大部分对入门级使用免费，但当你需要提升应用需求时对你进行收费。

* [Nitrous.io](https://www.nitrous.io/) 提供了一个云 IDE，同时提供的主机托管服务也能随着应用系统流量的提高而能助你进行扩展。

* [Cloud9](https://c9.io/) 最先是作为一个独立公司的，而现在它由 Amazon 所有，并作为了 Amazon Web Services 的一部分。

* [Terminal](https://www.terminal.com/) 是另一个云环境，除了 IDE 它还主推托管数据库服务。


## 开发环境相关资源
* 如果你是考虑基于云计算的开发环境的路线，那么看下 Lauren Orsini 的这篇文章 [Cloud9、 Koding 和 Nitrous.io 之比较](http://readwrite.com/2014/08/14/cloud9-koding-nitrousio-integrated-development-environment-ide-coding)。她还对什么是云 IDE 什么不是云 IDE 进行了深入的阐述。

* 《Real Python》上有一篇不错的文章，详细说明怎样 [设置你的 Sublime Text 3 环境](https://realpython.com/blog/python/setting-up-sublime-text-3-for-full-stack-python-development/) 使其成为一个功能完备的 IDE。

* [Python 漫游指南](http://docs.python-guide.org/en/latest/dev/env/) 上有一页专门讲述开发环境的内容。
  
* [选择最佳 Python IDE](http://pedrokroger.net/choosing-best-python-ide/) 是一篇针对六个 IDE 的评测文章。这篇文章认为 PyCharm、Wing IDE 和 PyDev 优于另外三个。 

* [PyCharm: 好的方面](http://nafiulis.me/pycharm-the-good-parts-i.html) 向你展示了如何更高效地利用该 IDE 来写代码。

* 如果你使用 PyCharm 这个 IDE 或者正考虑尝试一下，那么你应该读读 JetBrains 的 [PyCharm Blog](http://blog.jetbrains.com/pycharm/)。它的一位核心开发人员在播客
  [和我聊 Python](http://talkpython.fm/episodes/show/36/python-ides-with-the-pycharm-teama) 上的一篇采访也值得听一下。

* [PyCharm 对比 Sublime Text](https://opensourcehacker.com/2015/05/02/pycharm-vs-sublime-text/) 对这两个编辑器的多个功能进行了比较。

