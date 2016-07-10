title: 部署
category: page
slug: deployment
sortorder: 0701
toc: True
sidebartitle: 7. 部署
meta: Web 应用部署是一项涉及了应用打包并在服务器上运行的技术。快来 Full Stack Python 学习更多关于部署的知识吧。
translators: blog.chriscabin.com
updated: 2016-07-08 21:00

# 部署
部署是一项涉及了为你的 web 应用打包，并且在生产环境下运行的技术。


## 为何部署是必要的？
你的 web 应用必须存在于除了你的台式机或者笔记本之外的设备上。生产环境是指正式版本，它包含了你当前的应用及其相关数据。


## 部署主题框图
Python web 应用部署由多个环节构成，并且每个环节都需要独立配置好。下面这幅图清晰地描述了部署的各个环节是如何相互联系的。点击这幅图片可以获得对应的 PDF 版本。

<a href="/full-stack-python-map.pdf" target="_blank" style="border: none;"><img src="/img/full-stack-python-map.png" width="100%" alt="Full Stack Python site map." class="technical-diagram" /></a>


## 部署托管方案
这里提供了四种部署并托管 web 应用的方案：

1. [“裸机”服务器](/servers.html)

2. [虚拟化服务器](/servers.html)

3. [基础设施即服务（IaaS）](/servers.html)

4. [平台即服务（PaaS）](/platform-as-a-service.html)

前三种方案是类似的。开发者首先需要准备一台或多台安装了 Linux 发行版的服务器。然后要在服务器上安装系统程序包、Web 服务器、WSGI 服务器、数据库以及 Python 运行环境。最后，将从源码生成的应用安装到配置好的环境中即可。

需要注意的是，可以通过系统特定的程序包管理系统来安装一个 Python web 应用。因为它们是比较高级的部署技术，所以我们没有包含进来。


## 部署有关的资源
* 如果你需要一个渐进式的 Python web 应用部署指南，
  我刚好写了 [一本书](http://www.deploypython.com/) 是专门针对应用部署的，它叫
  [全栈 Python 指南之部署](https://gumroad.com/l/WOvyt)，
  会对你有很大的帮助。

* [部署 Python web 应用](http://talkpython.fm/episodes/show/26/deploying-python-web-applications-updated)
  是著名的“和我讨论 Python” 播客系列中的一节，我在那儿讨论了在基于很传统的虚拟私有服务器、Nginx 以及“绿色独角兽（Green Unicorn）” 的栈上部署 web 应用。

* [Web 应用部署沉思录](http://omniti.com/seeds/thoughts-on-web-application-deployment)
  讲解了应用部署的各个环节，包括源码控制，制定计划，持续部署以及监测结果等。

* [部署软件](https://zachholman.com/posts/deploying-software)
  是理解如何恰当地部署软件的必读长文。

* [持续部署实践](http://blogs.atlassian.com/2014/04/practical-continuous-deployment/)
  给出了交付与部署的定义，同时讲解了部署的流程图。

* 在这个 [Neal Ford 制作的免费视频](http://player.oreilly.com/videos/9781491908181?toc_id=210188) 中，
  他谈论了持续交付在工程上的实践。他解释了关于
  [持续集成](/continuous-integration.html)、持续部署和持续交付间的区别。极力推荐这部视频作为部署概念的综述，同时也是对这个系列视频的介绍。

* [在 Instagram 使用持续部署](http://engineering.instagram.com/posts/1125308487520335/continuous-deployment-at-instagram/)
讲述了他们在部署上的成长故事，即从单一的大结构脚本到持续部署的改进历程。在成长过程中，他们遭遇了在代码审查、测试失败、候选版本构建以及回滚这些方面的问题。这是一篇佳作，阐述了如何才能很好地部署大规模的 Python 应用。

* Stack Overflow 上关于 
  [他们如何部署](http://nickcraver.com/blog/2016/05/03/stack-overflow-how-we-do-deployment-2016-edition/) 的指南是一篇很有深度的文章，它涵盖了从 git 分支到数据库整合的有关话题。

* 如果你正在使用 Flask 的话，那么阅读这篇 [在 Ubuntu 上部署 Flask 应用详解](https://realpython.com/blog/python/kickstarting-flask-on-ubuntu-setup-and-deployment/)
  是让你熟悉部署过程的良好途径。


## 部署学习清单
1. 如果你赶时间的话，看看这个 
   [平台即服务（PaaS）](/platform-as-a-service.html) 方案吧。你可以以免费或者较低的成本部署一款低流量的 web 应用。相比使用传统服务器的方案，你根本不用担心设置操作系统及 web 服务器这样的问题。理论上来说，使用 PasS 托管，你可以更快地在网上看到你的 web 应用在运行。

1. [传统服务器方案](/servers.html) 是你学习完整的 Python 网络栈工作方式的最佳选择。随着你的应用规模逐渐扩大，相对使用 PaaS 方案，你会发现使用虚拟私有服务器通常会更省钱。

1. 阅读有关服务器、[操作系统](/operating-systems.html)、
   [web 服务器](/web-servers.html) 以及 [WSGI 服务器](/wsgi-servers.html) 的内容，从而对运行一款 Python web 应用需要配置那些组件有更宽泛的了解。
