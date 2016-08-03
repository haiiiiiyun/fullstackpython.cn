title: Ubuntu
category: page
slug: ubuntu
sortorder: 0725
toc: False
sidebartitle: Ubuntu
meta: Ubuntu 是一个基于 Debian Linux 的操作系统发行版，通常用于 Python 开发和部署。
translators: blog.chriscabin.com
updated: 2016-08-01 14:00


# Ubuntu
Ubuntu 是一个基于 Debian Linux 的操作系统发行版，通常用于 Python 开发和应用部署。


## 为何 Ubuntu 对 Python 很重要？
Ubuntu 是用于本地开发和服务器部署的最常用的 Linux 发行版之一。
一些 [平台即服务](/platform-as-a-service.html) 如 Heroku 就将 Ubuntu 作为基础操作系统，因此，作为一个 Python 开发者，你会经常使用 Ubuntu 或者类似的基于 Debian Linux 的操作系统进行工作。

<div class="well see-also">Ubuntu 是<a href="/operating-systems.html">操作系统</a> 概念的一种实现。在<a href="/deployment.html">部署</a> 章节学习更多的知识，或者查看所有主题的<a href="/table-of-contents.html">目录。</a></div>


## Ubuntu 的 LTS 是什么意思？
每两年，Ubuntu 都会发布一个长期支持（LTS）版本，它能够接收长达五年的更新，而非 LTS 发行版则只有两年更新支持。
然而，当前的 LTS 模型中存在一些问题，那就是你 [必须只使用来自主仓库的软件包](http://www.wilderssecurity.com/threads/ubuntu-lts-many-vulnerabilities-despite-long-term-support.385386/)，除非你打算手动解决非主仓库系统包的安全更新问题。


## 其它 Ubuntu 资源
* 使用这些针对 Ubuntu 16.04 LTS 的教程设置好你的 Python [开发环境](/development-environments.html)：
    * [如何在 Ubuntu 16.04 LTS 上设置 Python3、Flask 和 Green Unicorn](/blog/python-3-flask-green-unicorn-ubuntu-1604-xenial-xerus.html)。
    * [在 Ubuntu 16.04 LTS 上配置 Python 3、Bottle 和 Gunicorn 用于开发](/blog/python-3-bottle-gunicorn-ubuntu-1604-xenial-xerus.html)。
    * [在 Ubuntu 16.04 LTS 上设置 Python 3、Django 和 Gunicorn](/blog/python-3-django-gunicorn-ubuntu-1604-xenial-xerus.html)。

* 还有一些演示了如何在 Ubuntu 上配置相关数据库和 Redis：
    * [在 Ubuntu 16.04 上设置 PostgreSQL 使用 Python3 和 psycopg](/blog/postgresql-python-3-psycopg2-ubuntu-1604.html)。
    * [如何在 Ubuntu 16.04 上安装并使用 MySQL](/blog/install-mysql-ubuntu-1604.html)。
    * [如何在 Ubuntu 16.04 上使用含有 Python 3 和 redis-py 的 Redis](/blog/install-redis-use-python-3-ubuntu-1604.html)。

* Canonical，生成 Ubuntu 的组织，通常推动着非 LTS 版本的界限，但是偶尔也会针对一个 LTS 版本带来主要的改变。16.04 就是一个这样的版本，这篇文章描述了 [Ubuntu 16.04 证明了一个 LTS 发行版如何能够在 Linux 前沿生存下来的](http://arstechnica.com/information-technology/2016/05/ubuntu-16-04-proves-even-an-lts-release-can-live-at-linuxs-bleeding-edge/)。

* 在 Docker 项目初期，Ubuntu 一直被当做目标操作系统。这有一篇指南说明了 [如何在 Ubuntu 14.04 LTS 上安装 Docker](http://www.liquidweb.com/kb/how-to-install-docker-on-ubuntu-14-04-lts/)，这是一个较老的支持容器的操作系统版本。

* [我在服务器上的最初 10 分钟——Ubuntu 安全防护入门](http://www.codelitt.com/blog/my-first-10-minutes-on-a-server-primer-for-securing-ubuntu/)
基于较早的一篇博客，叫做 Linux 服务器上最初 5 分钟。这篇文章转为 Ubuntu Linux 而写，并且深入说明了用户账户、sudo 权限、SSH 秘钥、安全更新和双重认证。

* [在为 Ubuntu 提供安全防护时所学](https://major.io/2015/10/14/what-i-learned-while-securing-ubuntu/)
说明了在如何给一个操作系统提供安全防护时，仅仅查找正确信息就是怎样地困难。在这个例子中，作者回顾了他如何保证包管理安全性、安全标准和 Ubuntu 14.04 LTS 上的文件完整性。
