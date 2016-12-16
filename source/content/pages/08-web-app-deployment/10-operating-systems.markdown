title: 操作系统
category: page
slug: operating-systems
sortorder: 0705
toc: False
sidebartitle: 操作系统
meta: 快来 Full Stack Python 为你的 web 应用学习应当使用何种操作系统以及怎样配置操作系统的知识吧。
translators: blog.chriscabin.com
updated: 2016-07-12 08:00


# 操作系统
操作系统运行在服务器主机或者虚拟服务器主机上，并且控制计算资源的使用。操作系统当然也包括一种安装必要程序的途径，好让你的 Python web 应用能够运行。


## 为何操作系统是必要的？
操作系统使得我们觉得理所当然的许多计算任务变得简单。例如，操作系统能够写入文件、进行网络通信以及同时运行多个程序。否则的话，你需要自己完成底层的实现来控制 CPU、内存、网卡以及许多其它的硬件。

如果不使用现有的诸如 Linux、Mac OS X 或者 Windows 操作系统的话，那你就不得不为你的 web 应用编写一个新的操作系统。 如此一来，你就不可能再为你的 Python web 应用增加新功能了，因为你会忙于在你的汇编代码中追踪内存泄露问题，前提是你能够走到这一步。

幸运的是，开源社区为 Python 世界提供了坚若磐石的免费操作系统 Linux 来运行我们的应用程序。


## 操作系统推荐
唯一推荐用于在生产环境中部署 Python web 堆栈的操作系统是 Linux。有好几种常见的 Linux 发行版可以运行在生产服务器上。Ubuntu 长期支持版（LTS）、Red Hat Linux 企业版以及 CentOS 都是可行的选择。

Mac OS X 适合用于开发。 Windows 和 Mac 
OS X 都不适合在生产环境下部署，除非你有必须要替代 Linux 的充足理由。

### Ubuntu
Ubuntu 是由
[Canonical](http://www.canonical.com/) 公司推出的 Linux 发行版。 Ubuntu 软件包基于 Debian 发行版，包括这个 
[aptitude 包管理器](http://wiki.debian.org/Apt)。桌面版 Ubuntu 绑定了 GNOME（直到 11.04）或者 Unity（11.10 到现在）来提供用户界面。

Ubuntu [长期支持](https://wiki.ubuntu.com/LTS) (LTS) 发行版是推荐用于部署的发行版本。Canonical 会为 LTS 版本提供长达 5 年的后期更新支持。Canonical 每两年就会推出新的 LTS 发行版，这就为升级提供了非常方便的途径，同时灵活地允许在必要的情况下跳过其他的 LTS 发行版进行升级。截至 2016 年 4 月，
[16.04 Xenial Xerus](https://wiki.ubuntu.com/XenialXerus/ReleaseNotes)
是最新的 Ubuntu LTS 发行版。 Xenial Xerus 包括了
[Python 3.5](/python-2-or-3.html) 作为其默认的 Python 版本，与 Ubuntu 14.04 LTS 上的 2.7 版本相比，这是一个主要的更新。 


#### Ubuntu Python 软件包
在 Linux 服务器上有好几种
[Aptitude](https://help.ubuntu.com/12.04/serverguide/aptitude.html)
软件包来运行 Python 栈。这些包是： 

* [python-dev](http://packages.ubuntu.com/precise/python-dev) 用于头文件和 Python 静态库。

* [python-virtualenv](http://packages.ubuntu.com/precise/python-virtualenv)
  用于创建并管理 Python 
  [virtualenvs](https://virtualenv.pypa.io/en/latest/) 来隔离库的依赖。


### Red Hat 和 CentOS
[Red Hat Linux 企业版](http://www.redhat.com/products/enterprise-linux/)
(RHEL) 以及 [社区企业版操作系统](http://www.centos.org/)
(CentOS) 都是同一个发行版。这两个版本的主要区别是 CentOS 是开源的操作系统，它继承自 RHEL，并且是自由授权，免费使用的。

RHEL 和 CentOS 与基于 Debian 的 Linux 发行版相比，使用了不同的包管理器和命令行界面： RPM 包管理器（RPM）以及 
Yellowdog 更新，修改（YUM）。RPM 使用特殊的 .rpm 格式的文件来管理库以及应用程序的打包和安装。YUM
提供了命令行界面用于和 RPM 系统交互。


## 操作系统相关的资源
* [Linux 发行版是什么？我该怎样选择正确的发行版？](http://www.linux.org/threads/selecting-a-linux-distribution.4087/)

* [Linux 性能](http://www.brendangregg.com/linuxperf.html) 是一个很精彩的网站，上面有大量关注性能的资料链接，这些资料当你在任何的 Linux 发行版上开发或部署时都很有用。

* Lifehacker 的 [Linux 发行版选择指南](http://lifehacker.com/5889950/how-to-find-the-perfect-linux-distribution-for-you).

* [Linux 之旅](https://linuxjourney.com/) 是非常不错的 Linux 基础学习课程，比如可以学习命令行、包管理、文本处理。当然也有更多涉及高级话题的课程，比如内核是如何工作的，怎样设置日志以及管理设备。

* [Ops 学校课程](http://www.opsschool.org/en/latest/) 是学习 Linux 基本原理以及系统管理员通常会怎样开展工作的综合资源。

* 既然你的将要使用 Linux 作为生产环境下的操作系统，那么熟悉 Unix/Linux 命令和它的哲学就是非常重要的事情了。学习
  [这篇 Unix 教程](http://www.oliverelliott.org/article/computing/tut_unix/)
  来对这个操作系统更加熟悉。

* [使用服务器的最初 5 分钟](http://plusbryan.com/my-first-5-minutes-on-a-server-or-essential-security-for-linux-servers)
  说明了最初几个需要在你使用的任何服务器上应当手动或者自动完成的 [安全步骤](/web-application-security.html)。

* “数字海洋（Digital Ocean）”有一篇文章详细介绍了
  [在 Ubuntu 上配置 Python web 应用的步骤](https://www.digitalocean.com/community/articles/how-to-set-up-ubuntu-cloud-servers-for-python-web-applications)。

* [深入 Linux](http://0xax.gitbooks.io/linux-insides/content/index.html) 是一系列讲解 Linux 在幕后是如何工作的文章，它从低层的启动过程开始介绍。


## 操作系统学习清单
1. 选择一款 Linux 操作系统，可以是基于 Debian 的发行版如 Ubuntu，或者是基于 Fedora 的发行版如 CentOS。

1. 通过一些基础的步骤加强系统的安全性。 安装一些基本的安全软件包，如 
   [fail2ban](http://www.fail2ban.org/wiki/index.php/Main_Page) 和
   [unattended-upgrades](https://help.ubuntu.com/community/AutomaticSecurityUpdates)。
   创建一个拥有 sudo 特权的新用户，并且禁用 root 登录。禁止仅使用密码登录选项，并且使用一个公私钥对来替换。 阅读下面列出的更多关于增强系统安全的资源。

1. 安装特定的 Python 软件包为 Python 应用准备好运行环境。根据你选择的发行版来安装所需要的软件包。

1. 仔细阅读 [web 服务器](/web-servers.html)，因为部署环节中的下一个就是安装一个 web 服务器。 

