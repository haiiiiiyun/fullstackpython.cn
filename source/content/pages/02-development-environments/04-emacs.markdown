title: Emacs
category: page
slug: emacs
sortorder: 0204
toc: False
sidebartitle: Emacs
meta: Emacs 是一个可扩展，易定制的文本编辑器，通常用于编写代码。 在 Full Stack Python 上了解更多 Emacs 知识。
authors: haiiiiiyun.github.io
updated: 2016-06-06 20:43


# Emacs
Emacs 是一个可扩展的文本编辑器，可以通过编写 Lisp 代码来定制。

## 为什么说 Emacs 适合用来编写 Python 代码？
Emacs 旨在可以通过内置的 Lisp 解释器和包管理器进行定制。它的包管理器叫 package.el，具有安装管理功能。其最大的 Lisp 软件包仓库是 [Melpa](http://melpa.org)，它能获取软件源上的数据并提供自动更新。

在 Emacs 中，宏对于执行重复的动作非常有用。宏就是对之前一组按键序列的记录，并通过重放该记录来执行之前的动作。

所谓挂勾，就是包含一组可调用函数的 Lisp 变量，它是 Emacs 的一种扩展机制。例如，``kill-emacs-hook`` 能在 Emacs 退出前运行，从而使那些函数能被导入到那个挂勾中，以便在退出工作完成前执行必要的操作。 

<div class="well see-also">当你在阅读有关使用 Emacs 编写 Python 代码的知识时，可以去了解下使用何种<a href="/web-frameworks.html">Web 框架</a> 及 <a href="/deployment.html">如何部署一个应用</a>。</div>


## 常用 Emacs 资源
* [GNU Emacs Manual](http://www.gnu.org/software/emacs/manual/html_node/emacs/index.html) 是一份官方文档，就如何使用 Emacs 提供了深入的探讨。

* [Emacs as a Python IDE](http://www.jesshamrick.com/2012/09/18/emacs-as-a-python-ide/) 就如何设置 Emacs 以成为一个 Python 开发环境进行了详细的示例说明。

* [Emacs - the Best Python Editor?](https://realpython.com/blog/python/emacs-the-best-python-editor/) 是《Real Python》系列上的精彩文章，讲述了如何使用编辑器。除了这篇 Emacs 文章，上面还有一些针对 Python 开发的 [Vim](https://realpython.com/blog/python/vim-and-python-a-match-made-in-heaven/) 和 [Sublime Text 3](https://realpython.com/blog/python/setting-up-sublime-text-3-for-full-stack-python-development/) 的文章。

* [Emacs Redux](http://emacsredux.com/) 这篇博文提供了如何有效使用 Emacs 的建议及技巧。

* [Emacs Rocks](http://emacsrocks.com/) 是关于 Emacs 的视频教程系列。

* [What the .emacs.d?!](http://whattheemacsd.com/) 提供了一堆 Emacs 工作流程的优化方法。


## 著名的 Elisp 软件包
* [Magit](https://magit.vc/) 能让用户在 Emacs 中检查和修改 Git 仓库。

* [company-mode](http://company-mode.github.io/) 发明了一种模块化的内存代码补全框架。

* [Flycheck](http://flycheck.github.io/) 提供语法检查。

* [anaconda-mode](https://github.com/proofit404/anaconda-mode/) 专用于 Python 开发，允许进行代码浏览跳转、文档查找和代码补全。其核心使用 [jedi](http://jedi.jedidjah.ch/en/latest/) 库实现。

* [Tern](http://ternjs.net/) 是一个独立的 JavaScript 代码分析引擎。它能通过 [tern-django](https://github.com/proofit404/tern-django) 包与 Django 项目进行整合。

## 流行的用户配置
* [Prelude](https://github.com/bbatsov/prelude) 是一个 Emacs V24 的增强版。

* [A reasonable Emacs config](https://github.com/purcell/emacs.d) 展示了一套功能完备的 Emacs 配置方案。

* [Emacs settings](https://github.com/magnars/.emacs.d) 这个库包含了 Emacs Rocks 上的屏幕录像里用到的所有 Emacs 配置。

* [Spacemacs](https://github.com/syl20bnr/spacemacs) 整合了 Emacs 的扩展性和 Vim 的符合人体工程学的文本编辑功能。
