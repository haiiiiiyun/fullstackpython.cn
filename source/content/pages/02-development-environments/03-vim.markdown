title: Vim
category: page
slug: vim
sortorder: 0203
toc: False
sidebartitle: Vim
meta: Vim 是一个具有强大字符处理能力的文本编辑器。到 Full Stack Python 网站上找到更多 Vim 资料。
authors: haiiiiiyun.github.io
updated: 2016-06-03 08:20


# Vim
Vim， 即 Vi IMproved 的缩写，是一个可配置的文本编辑器，通常用作 Python 的开发环境。Vim 用户通常使用大量的插件、Vim 脚本和逻辑命令语言来扩展 Vim 功能。

## 为什么 Vim 适合用作 Python 开发环境
Vim 的哲学是：当开发人员的手不离开键盘时，工作效率会更高。代码应该从开发人员的头脑自然地流经键盘，再到达屏幕。使用鼠标等外设会降低开发者的思想与代码的转换速率。

Vim 内含一种逻辑结构化的命令语言。当开始学习时，我们会觉得理解全部的命令是不可能的。但是，这些命令是按一定逻辑组织起来的，因此，随着时间推移，这个编辑器会变得得心应手。

<div class="well see-also">如果你喜欢 Vim，你应该也想了解 <a href="/development-environments.html">写代码的开发环境</a> 和 <a href="/why-use-python.html">什么使 Python 变得如些强大</a>。</div>


## 利用 Vimrc 配置 Vim
Vimrc 是 Vim 编辑器的配置文件。一个 Vimrc 文件可以是一个空文件，也可以包含成百上千行配置命令。

下面是我用于 Python 开发的一个简短的 .vimrc 示例文件，并附带注释。从中你可以感受一下它的配置语句：

    " 开启语法高亮
    syntax enable

    " 显示行号
    set number

    " 设置 tab 符为 4 个空格
    set ts=4

    " 写代码时，移到下一行时自动缩进
    set autoindent

    " 将 tab 符自动扩展成空格
    set expandtab

    " 使用 >> 和 << 命令时, 移动 4 个空格
    set shiftwidth=4

    " 在光标所在的当前行下显示一条行指示线
    set cursorline

    " 显示 [] {} 和 () 匹配的另一半符号
    set showmatch

    " 开启全部 Python 语法高亮特性
    let python_highlight_all = 1

下面的图片是我在 Mac OS X 上编辑本页 markdown 文件的截图，你可以这到这些配置选项在暗色背景后的显示效果是什么样的。

<img src="/img/vim-dark-bg.jpg" width="100%" alt="在暗色背景上设置了基本配置选项的 Vim 。" class="technical-diagram" style="border-radius: 5px;">

看一下另一个例子，同样的配置选项，这次使用的是浅色背景，图片是我在写 [制作交互的演示文稿](https://github.com/makaimc/choose-your-own-adventure-presentations) 项目的 Python 代码时的截图。

<img src="/img/vim-white-bg.png" width="100%" alt="在浅色背景上设置了基本配置选项的 Vim 。" class="technical-diagram" style="border-radius: 5px; border: 1px solid #999;">

Vimrc 文件位于运行 Vim 的用户帐号的 home 目录下。例如，我的用户账号是 'matt'， 在 Mac OS X 上，我的 Vimrc 文件可以在 ``/home/matt/`` 目录下找到。

如果 Vimrc 文件还没有创建，你只需在用户的 home 目录下创建一个即可，这样，当你下次打开 Vim 时，它就能被加载了。

## Vim 教程
Vim 有难学的坏名声，但是通过这些教程，入门会变得更加容易。

* [Learn Vim Progressively](http://yannesposito.com/Scratch/en/blog/Learn-Vim-Progressively/) 是一本很精彩的教程，里面提到的学习方式和我学习 Vim 时用的是一样的：先学会编辑器的基本知识就会日常使用，然后再学习更加高级的命令。

* [A vim Tutorial and Primer](https://danielmiessler.com/study/vim/) 深入研究了如何从初学者进阶到 Vim 专家。

* [Why Atom Can't Replace Vim](https://medium.com/@mkozlows/why-atom-cant-replace-vim-433852f4b4d1) 探讨了 Vim 的一个核心理念： 命令的可组合性。Vim 的内置语言能将简单的命令组合成一个更加高级的组合操作命令。例如在命令模式下， `$` 的功能是移动到行尾，但当 `$` 前加 `d` 后，就能删除从当前位置到行尾的所有内容。随着时间的推移，这些简单的命令会变成你的直觉，而组合命令会比在下拉菜单中设置一个特定选项来删除到行尾的全部内容这样的方式更加强大。

* [Vim as a Language](http://benmccormick.org/2014/07/02/learning-vim-in-2014-vim-as-language/) 解译了其语言语法及如何通过日积月累掌握这个编辑器。

* [How to install and use Vim on a cloud server](https://www.digitalocean.com/community/tutorials/installing-and-using-the-vim-text-editor-on-a-cloud-server) 和 [How to use Vim for advanced editing of code on a VPS](https://www.digitalocean.com/community/tutorials/how-to-use-vim-for-advanced-editing-of-plain-text-or-code-on-a-vps--2) 这两份详细教程都来自 Digital Ocean，内容是如何设置和运行 Vim，无论你是在本地还是在云服务器上使用 Vim, 都值得一看。

* [Vim 冒险](http://vim-adventures.com/) 是一款小巧好玩的浏览器游戏，通过玩这个冒险游戏能帮你学习 Vim 命令。

* 在 [Vim: revisited](http://mislav.uniqpath.com/2011/12/vim-revisited/) 中， 作者解释了他时断时续使用 Vim 的经历。然后阐述他如何配置和使用该编辑器，并坚持以它作为主要的代码编辑工具。

## Vimrc 资源
这些是学习如何组织 `.vimrc` 文件的资源。我建议一项项增加配置选项，每次添加一条，然后再单独测试一下，而不是一股脑儿地把你不熟悉的 Vimrc 都拷贝进来。

* [A Good Vimrc](http://dougblack.io/words/a-good-vimrc.html) 是一份关于配置 Vim 的即详细又独特的指南。我极力推荐给新手和有经验的 Vim 用户。

* [Vim and Python](https://justin.abrah.ms/vim/vim_and_python.html) 阐述了多个只针对 Python 的 .vimrc 选项。

* 该 [代码库的 Vimrc 文件目录](https://github.com/amix/vimrc/tree/master/vimrcs) 下有很多配置示例，里面都有详细注释，易于学习。

* 对于那些入门 Vim 有困难的朋友，看下这篇文章 [两个简单步骤让这位仁兄学会了 Vim](http://adamdelong.com/two-simple-steps-helped-me-learn-vim/)。

## Vim 安装指南
这些安装指南将指导你在 Mac OS X、Linux 和 Windows 上安装和运行 Vim 。

* [Upgrading Vim on OS X](http://www.prioritized.net/blog/upgrading-vim-on-os-x) 阐述了为什么要从 Vim 7.2 升级到 7.3+，以及如何通过 [Homebrew](http://brew.sh/) 升级。


* 在 Windows 7+ 上安装 Vim 的最简单方法是下载并运行 [gvim74.exe](http://www.vim.org/download.php#pc) 文件。

* 在 Linux 上应该使用 ``sudo apt-get install vim`` 来安装 [vim 软件包](https://launchpad.net/ubuntu/+source/vim)。

* 如果你将 PyCharm 作为你的 IDE 的话，你不需要再单独安装 Vim 文本编辑器。你可以用 PyCharm 的 [IdeaVim](https://plugins.jetbrains.com/plugin/164)  插件，并利用 ~/.ideavimrc 及其它的 Vim 模拟功能来实现 Vim 按键绑定、视觉/插入模式等。 

## 将 Vim 作为 Python IDE
一旦你已熟悉 Vim 编译器，就可以用一些配置选项和插件来提高你的 Python 工作效率。到了这一步，你可以看下这些资料：

* [VIM and Python - a Match Made in Heaven](https://realpython.com/blog/python/vim-and-python-a-match-made-in-heaven/) 详细叙述了如何为 Python 的日常工作设置一个强大的 Vim 环境。

* [python-mode](https://github.com/klen/python-mode) 是一个 Vim 插件项目， 具有语法高亮、断点、PEP8 代码检测、代码补全、以及其它许多你能在集成开发环境中看到的功能。

* [Vim as Your IDE](http://haridas.in/vim-as-your-ide.html) 探讨了当你学会了 Vim 的基本用法后如果设置 Vim 以提高工作效率。

* [Vim as a Python IDE](http://unlogic.co.uk/2013/02/08/vim-as-a-python-ide/) 讲述了将 Vim 打造成一个更加舒适的 Python 开发环境需要经历的几个必要步骤。

* [Setting up Vim for Python](http://stackoverflow.com/questions/9172802/setting-up-vim-for-python) 是 Stack Overflow 上针对如何入门 Vim 的一份不错的答案。

* 如果你用 Vim 写 Markdown 文本，务必看下这篇 [颇有见地的文章：设置 Vim 以支持 Markdown](http://www.swamphogg.com/2015/vim-setup/)。


## Vim 插件管理
* [Vundle](https://github.com/gmarik/Vundle.vim) 是一个被大量推荐的 Vim 插件管理器。

* [Pathogen](https://github.com/tpope/vim-pathogen) 是一个广泛使用的插件管理器。

* [Vim-plug](https://github.com/junegunn/vim-plug) 宣称自己是一个最小的 Vim 插件管理器。


## Vim 插件资源
* [极大提升了我的工作效率的 5 个必备 Vim 插件](http://joelhooks.com/blog/2013/04/23/5-essential-vim-plugins/) 总结了作者对 Vundle、 NERDTree、 ctrlp、 Syntastic 和 EasyMotion 等 Vim 插件的使用心得。

* [Getting more from Vim with plugins](http://benmccormick.org/2014/07/21/learning-vim-in-2014-getting-more-from-vim-with-plugins/) 上提供了一份插件列表，并附有每个插件的使用说明。下面的评论内容也非常有趣，因此针对文章里提到的一些插件，一些人提供了类似的其他插件。

* [Powerline](https://github.com/powerline/powerline) 是一个流行的 Vim 状态栏插件，兼容 Python 2 和 3 。

