title: 平台即服务（PaaS）
category: page
slug: platform-as-a-service
sortorder: 0704
toc: False
sidebartitle: 平台即服务（PaaS）
meta: 使用 PaaS 部署应用代码的方案会有其它方面需要权衡的风险。快来 Full Stack Python 学习更多相关知识吧。
translators: blog.chriscabin.com
updated: 2016-07-11 10:25


# 平台即服务（PaaS）
平台即服务（PaaS）提供了硬件基础设施和软件层，这样可以在它上面部署 web 应用。使用 PaaS 方案部署你的 web 应用，就意味着你不必了解更多关于服务器基础、操作系统、web 服务器、以及常提到的 WSGI 服务器的相关知识。

*注意*：如果你对使用 PaaS 方案部署 web 应用没什么兴趣的话，可以去阅读 [WSGI 服务器](/wsgi-servers.html) 一节的内容。

PaaS 层定义了应用程序应该如何访问诸如计算时间、文件以及外部服务这样的资源。相对于在一台服务器或者在 IaaS 上部署应用的方案，PaaS 为使用计算资源提供了更高层次的抽象。

使用 PaaS 方案使得部署和操作变得更加简单，因为它会强迫开发者让应用程序符合 PaaS 架构。例如，在部署应用期间，Heroku 会在仓库的基目录查找 Python `requirements.txt` 文件，因为基目录就是那个文件的实际社区标准位置。

<img src="/img/servers-versus-paas.png" width="100%" alt="传统 LAMP 服务栈对比基础设施即服务（PaaS）栈" class="technical-diagram" />

如果你走的是使用 PaaS 的路线，那你就可以跳过配置操作系统和 web 服务器的步骤，它们都由 PaaS 预先配置并提供了。 PaaS 提供的服务通常起始于 WSGI 服务层。


## 平台即服务（PaaS）的职责所在
虽说 PaaS 提供的服务会简化服务器、操作系统和 web 服务器的设置和维护，但开发者们仍然需要对他们的 web 栈中其他各层负责。

虽然了解一些用于支撑你的 PaaS 的操作系统知识是有好处的，例如 Heroku 使用的是 Ubuntu 10.04，但是你不必学习很多关于操作系统和服务器层面的安全知识。然而，部署到 PaaS 的 web 应用在在作为 LAMP 堆栈上的应用层依然会因为安全漏洞而易受攻击。这依旧是你的职责去保证你的 web 应用框架和应用能够及时更新并且保证它们的安全。阅读
[安全部分](/web-application-security.html) 获取更多信息。


## 支持 Python 的平台即服务（PaaS）
* [Heroku](http://www.heroku.com/)

* [Google App Engine](https://developers.google.com/appengine/)

* [Gondor](https://gondor.io/)

* [PythonAnywhere](https://www.pythonanywhere.com/)

* [OpenShift](https://openshift.redhat.com/community/get-started/python)

* [AWS Elastic Beanstalk](https://aws.amazon.com/elasticbeanstalk/)


## 与平台即服务（PaaS）有关的资源
* [PaaS 测评：对比在 Stackato, OpenShift, Dotcloud 和 Heroku 上托管和部署 Django 应用](http://appsembler.com/blog/paas-bakeoff-comparing-stackato-openshift-dotcloud-and-heroku-for-django-hosting-and-deployment/) ，由 [Nate Aune](https://twitter.com/natea) 编写。

* [部署 Django](http://www.rdegges.com/deploying-django/) 由
  Randall Degges 编写， 是另外一篇有关 Heroku 的免费并且优秀的文章。

* [浅说 AWS](https://www.expeditedssl.com/aws-in-plain-english)
  说明了当前 Amazon Web Services 的独立服务的称呼，以及它们应当称呼什么才能让用户觉得更加清晰。

* [5个你应当避免的 AWS 错误](https://cloudonaut.io/5-aws-mistakes-you-should-avoid/)
  说明了普通的新手的在进行一些诸如手工管理设施、不使用扩展组以及未充分利用实例这样的实践时是如何产生问题的，你最好同时避免这些问题。
 
* Heroku 的
  [Python 部署文档](https://devcenter.heroku.com/articles/getting-started-with-python)
   提供了清晰的例子展示了如何使用 virtualenv, pip 和 `requirements.txt` 将应用部署到他们的平台。

* Miguel Grinberg 编写的 Flask 教程中包含了一篇完整的文章讲述了部署
  [Flask 应用到 Heroku](http://blog.miguelgrinberg.com/post/the-flask-mega-tutorial-part-xviii-deployment-on-the-heroku-cloud)。

* 由 
  [Randall Degges](https://twitter.com/rdegges) 编写的 DevOps Django 系列是学习使用 Heroku 服务非常好的阅读资料：

    * [第一部分：目标](http://www.rdegges.com/devops-django-part-1-goals/)
    * [第二部分：部署之痛](http://www.rdegges.com/devops-django-part-2-the-pain-of-deployment/)
    * [第三部分：Heroku 方式](http://www.rdegges.com/devops-django-part-3-the-heroku-way/)
    * [第四部分：选择 Heroku](http://rdegges.com/devops-django-part-4-choosing-heroku)

* [在 AWS Elastic Beanstalk 上部署 Django 应用](https://realpython.com/blog/python/deploying-a-django-app-to-aws-elastic-beanstalk/)
  是一篇非常精辟的文章，讲述了如何在 Amazon Web 服务提供的 PaaS 上进行部署。

* [三步完成部署：针对 AWS 和 Elastic Beanstalk 的介绍](https://news.mlh.io/deploy-your-hack-in-3-steps-intro-to-aws-and-elastic-beanstalk-02-20-2015)
  展示了如何部署一个简单的 Ruby Sinatra 应用，但是这些步骤对于 Python web 应用来说通常也是适用的。

* 你还在为在一个类似 Heroku 的平台即服务（PaaS）上部署一个合理大小的产品应用的花费而纳闷吗？ 看看 Cushion 的
  [透明开销清单](http://cushionapp.com/expenses/)，它们包含了使用 PaaS 以及其它服务的开支详情。
  
* 这篇 [新手指南：在 AWS 上扩展支持 1100 万用户](http://highscalability.com/blog/2016/1/11/a-beginners-guide-to-scaling-to-11-million-users-on-amazons.html)
  是一些非常有用的服务清单。当你的应用从拥有 10 人、100 人到 1000 人再到 50 万人以及超过百万用户后，你需要去阅读这篇指南。

* [如何隔离你的 AWS 产品和开发账户](http://blog.codeship.com/separate-aws-production-and-development-accounts/)
  是一篇基础的文章，讲述了如何将开发者沙盒账户和产品级别的 AWS 环境保持隔离。

* [Spotify 给 Google 云支付了多少？](https://medium.com/@davidmytton/how-much-is-spotify-paying-google-cloud-ebb3bf180f15)
  深入洞悉了 Spotify 如何在 Goole 云上运行它们所有的基础设施服务，并假想了它们要为此可能支付的费用。

* 有两篇博客是关于 AWS 自动扩展功能的， 它们分别是 [自动使用等价的 Spot 实例替换自动扩展的节点](https://mcristi.wordpress.com/2016/04/21/my-approach-at-making-aws-ec2-affordable-automatic-replacement-of-autoscaling-nodes-with-equivalent-spot-instances/)
  以及
  [自动扩展的节点：在实践中学习](https://mcristi.wordpress.com/2016/04/27/automatic-replacement-of-autoscaling-nodes-with-equivalent-spot-instances-seeing-it-in-action/)
  提供了一种很复杂但潜在方法来让 AWS 更加便宜，不过这取决于你的大多数花费是否在计算节点上。


## 平台即服务（PaaS）学习清单
1. 回顾上述列出的一些潜在的 Python 平台即服务（PaaS）选项。

1. 找一个最适合你的应用需求的 PaaS 供应商，并在那儿注册一个账户。Heroku 是推荐给初学者的 PaaS 选择，因为它提供了详细的文档，并且在网上有很多不错的教程。当然，其他的选择也是可行的，因为他们的目的就是让应用部署尽可能地简单。

1. 在 PaaS 上部署应用后，检查一下是否有任何需要的 PaaS 相关的详细配置文件，从而让你的应用以适当的方式运行。

1. 在 PaaS 上部署应用。

1. 将你的应用配置与数据库同步。

1. 为你应用的 [静态内容](/static-content.html) 设置内容分发网络（CDN）
  ，除非你的 PaaS 供应商已经帮你完成了这个部署步骤。

1. 检查你的应用是否正常工作，并在必要时进行调整。
