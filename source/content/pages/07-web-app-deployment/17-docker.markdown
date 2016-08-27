title: Docker
category: page
slug: docker
sortorder: 0717
toc: False
sidebartitle: Docker
meta: Docker 是一个容器管理系统，通常用于部署 web 应用。快来 Full Stack Python 学习更多关于 Doker 的知识吧！
translators: blog.chriscabin.com
updated: 2016-07-26 10:35


# Docker
Docker 是一个 [开源](https://github.com/docker/docker) 的基础设施管理平台，用于运行和部署软件。由于 Docker 平台总在不断地演进，所以确切的定义也会不断地变化。


## Docker 为何很重要？
Docker 能够将应用及其必要的操作系统依赖打包，从而可以轻易地部署在各种环境中。
从长远来看，Docker 具有成为轻松管理运行在各种类型服务器上的容器抽象层的潜力，不管服务器是否位于 Amazon Web 服务中、Google 计算引擎上、Linode 上、Rackspace 上或者其它地方。


## Docker 映像中的 Python 项目
* 这个 Docker 映像包含了
  [一个已经配置好的运行在 uWSGI 和 Nginx 上的 Flask 应用](https://github.com/tiangolo/uwsgi-nginx-flask-docker).
  你也可以瞧瞧 [Docker hub 中的映像](https://hub.docker.com/r/tiangolo/uwsgi-nginx-flask/)。

* [最小的-docker-python-设置](https://github.com/OrangeTux/minimal-docker-python-setup) 
  包含了一个使用 Nginx、uWSGI、Redis 和 Flask 的映像。

## Docker 相关资源
* [Docker 是什么以及什么时候使用它](http://www.centurylinklabs.com/what-is-docker-and-when-to-use-it/)
  清晰地揭露了 Docker 是什么和不是什么。当你的大脑第一次被 Docker 概念萦绕时，不妨读一下这篇不错的文章。

* [Andrew Baker](https://github.com/atbaker) 在 [PyOhio](http://andrewtorkbaker.com/pyohio-docker-101-tutorial) 上发表了一篇非常出色的教程，是关于
  [初学者和进阶者使用 Docker](https://github.com/atbaker/docker-tutorial) 的。
  Andrew 也写了一篇文章 [容器可以为你做什么](http://radar.oreilly.com/2015/01/what-containers-can-do-for-you.html)，
  并且还创建了非常值得购买的
  [O'Reilly Docker 介绍视频](http://shop.oreilly.com/product/0636920035732.do) 。

* [Docker 课程](http://prakhar.me/docker-curriculum/) 是一位开发者创建的非常详细的教程，旨在说明依赖 [Elasticsearch](https://www.elastic.co/) 的应用部署的详细步骤。

* [如何安装 Docker 并初步了解它](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-getting-started)
  演示了如何在 Ubuntu 13.04 系统上安装并开始使用 Docker 做开发。

* [它的确就是未来](http://blog.circleci.com/it-really-is-the-future/)
  探讨了 Docker 究竟只是一大堆炒作还是真正未来的基础设施自动化趋势。 这篇文章非常不错，可以了解为什么这些工具非常重要的来龙去脉。

* [Docker 安装方法](https://github.com/odewahn/docker-jumpstart/) 是一篇综合性的介绍，说明了什么是 Docker 以及如何开始使用这个工具。

* 如果你想在 Mac OS X 上快速使用 Docker，看看这些简明的指导
  [60 秒内在 OS X 上设置你的 Docker 工作流程](https://www.twilio.com/blog/2015/07/docker-workflow-on-osx-in-60-seconds.html)。

* [到底什么是 Docker](http://pythonforengineers.com/what-the-bleep-is-docker/)
  使用了非常通俗易懂的话配合例子说明了 Docker 提供了什么功能以及它在你的环境中能用来做什么。

* [Docker 实践 —— 为工程师准备的指南](https://zwischenzugs.wordpress.com/2015/03/14/docker-in-practice-a-guide-for-engineers/)
  是一份以早期可访问格式呈现的解释，讲述了 Docker 的概念和设计哲学，由新 Manning Docker 一书的作者编写。

* [8 种 Docker 开发模式](http://www.hokstad.com/docker/patterns)
  分享了一些专业课程，并解释了如何使用容器进行工作，从而能够在开发过程更多地使用容器。

* [从草稿构建 Docker 容器](http://datakurre.pandala.org/2015/07/building-docker-containers-from-scratch.html)
  是一个简明的教程，讲解了如何使用一份特定的配置创建一个 Docker 容器。

* [在使用 Docker 容器时应当避免的 10 件事](http://developerblog.redhat.com/2016/02/24/10-things-to-avoid-in-docker-containers/)
  提出了很多你“不该做”的一些事情，你需要在超出怎样使用容器的限制前考虑这些事情。


## 针对 Python 的 Docker 资源
* [利用 Docker 托管 Python WSGI 应用](http://blog.dscpl.com.au/2014/12/hosting-python-wsgi-applications-using.html)
  说明了如何在 WSGI 应用开发中使用 Docker，特别是使用 mod\_wsgi。

* [如何容器化 Python Web 应用](https://www.digitalocean.com/community/tutorials/docker-explained-how-to-containerize-python-web-applications)
  是一个内容丰富的教程，它使用了一个 Flask 应用并使用了一个 Docker 容器来部署该应用。

* 这个 [令人敬畏的 Docker](http://pritishc.com/blog/2015/09/03/docker-is-awesome/) 
  短系列文章说明了如何获得一个运行在 Docker 中的 Django + AngularJS 应用。
  [第二部分](http://pritishc.com/blog/2015/09/04/docker-is-awesome-part-ii/) 
  则延续了这个教程。

* [Docker 实战——更胜任、更开心、更有生产效率](https://realpython.com/blog/python/docker-in-action-fitter-happier-more-productive/)
  是一个杀手级教程，说明了如何将 Docker 和 CircleCI 合并在一起持续部署 Flask 应用。

* [在 Docker 中部署 Django 应用](http://handlebarcreative.tumblr.com/post/104881545637/deploying-django-applications-in-docker)
  说明了一些使用 Docker 对 Python 应用进行部署背后的概念，并特别讲解了如何使用 Docker 部署 Django 应用。
  
* [Docker 入门——从零开始到运行 Django 应用](https://ochronus.com/docker-primer-django/)
  提供了使用 Docker 和 Vagrant 运行 Django 应用特定的命令及其应有的输出。

* [使用 Docker 及 Docker Compose 替换 virtualenv](https://www.calazan.com/using-docker-and-docker-compose-for-local-django-development-replacing-virtualenv/)
  是一个讲解使用 Docker 替代 virtualenv 隔离依赖的教程。

* Lincoln Loop 撰写了
  [走近 Docker](https://lincolnloop.com/blog/closer-look-docker/)
  ，他是以 Python 开发者处理部署问题的视角撰写的。

* 对如何将 pip 和 Docker 结合很好奇？读读这篇文章
  [使用 Docker 高效管理 Python 项目依赖](https://jpetazzo.github.io/2013/12/01/docker-python-pip-requirements/)。

* [Python 虚拟环境与 Docker](http://blog.dscpl.com.au/2016/01/python-virtual-environments-and-docker.html)
  详细叙述了是否要在 Docker 中使用虚拟环境，以及系统包如何通常是一条更安全的路线。
