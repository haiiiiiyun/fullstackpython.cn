title: 持续集成
category: page
slug: continuous-integration
sortorder: 0713
toc: False
sidebartitle: 持续集成
meta: 当开发者们提交代码时，持续集成（CI）会自动重新构建、测试并部署应用。
translators: http://blog.chriscabin.com
updated: 2016-07-22 13:00

# 持续集成
持续集成可以让构建、测试和部署应用自动完成。不管是由个人还是整个团队创建的软件项目，通常都会以持续集成为中心，来确保重要的步骤（如单元测试）都自动化完成了，而不是用手工处理。

## 持续集成为何重要？
当把持续继承（CI）作为软件项目开发过程中的一个步骤后，就可以大大减少部署时间，因为持续集成将那些需要人工干预的步骤次数最小化了。使用 CI 的小缺点有两处：第一，开发者需要花费一定的时间进行初始化设置；第二，如果一个项目被拆分成了多个部分，比如从单一架构到 [微服务](/microservices.html) 架构，就会有一些不间断的维护工作。


## 自动化测试
使用 CI 的另外一个主要的优势是测试可以在部署过程中自动完成。
当开发者们检查源码库中的代码时，可以通过运行一个综合的测试套件 [unit](/unit-testing.html) 和 
[集成测试](/integration-testing.html) 来防止部署受损的问题发生。在检查期间，任何由测试套件捕获的偶然出现的 bug 都会报告出来，从而阻止部署过程继续。

源码审查中的自动化测试就像是保龄球保险杠，可以防止代码质量偏离正规。整合了单元和集成测试的 CI 可以保证任何代码修改都不会破坏现有的测试，从而确保软件能够按照预期工作。

## 持续集成的例子
下面的这幅图片从更高的层面说明了持续集成和部署是如何工作的。

<img src="/img/continuous-integration.png" width="100%" class="technical-diagram" alt="One potential way for continuous integration to work with source control and a deployment environment." />

如上图所示，当新的代码合并到源码库后，就会触发一个钩子来通知持续集成服务器有新的代码需要构建（如果通知功能不可用，持续集成服务器也可以采用轮询代码库的方式）。

持续集成服务器会获取到代码然后构建并测试。如果所有的测试都通过了，持续集成服务器就开始部署过程。新的代码会被同步到正在进行部署操作的服务器上。最后，通过重启服务以及相关的部署活动后，便完成了部署过程。

持续集成服务器和部署还有其它的结构图，以上仅是一种设置相对简单的例子。

## 开源持续集成（CI）项目
有很多种可以根据需要进行配置的免费开源持续集成服务器。

需要注意的是，其中有很多服务器都不是用 Python 实现的，但是可以很好地与 Python 应用配合使用。Polyglot 组织（使用超过一种语言和生态系统的组织）经常为他们的项目使用单一的集成服务器，而不管这些项目是用什么语言实现的。

* [Jenkins](http://jenkins-ci.org/) 是一个常见的 CI 服务器，用于在测试和生产服务器上构建并部署。
  [Jenkins 在 GitHub 上的源码库](https://github.com/jenkinsci/jenkins)。

* [Go CD](http://www.go.cd/) 是由
  [ThoughtWorks](http://www.thoughtworks.com/) 打造的 CI 服务器，设计采用了针对构建、测试和发行周期的最佳实践。
  [Go CD 在 GitHub 上的源码库](https://github.com/gocd/gocd)。

* [Strider](http://stridercd.com/) 是使用 node.js 编写的 CI 服务器。 
  [Strider 在 GitHub 上的源码库](https://github.com/Strider-CD/strider)。

* [BuildBot](http://buildbot.net/) 是一个持续集成 **框架**，含有一个用于创建你自己的 CI 服务器的组件集合。它使用 Python 来实现，并专为那些在构建和部署流水线中需要更多控制的开发团队打造。
  [BuildBot 在 GitHub 上的源码库](https://github.com/buildbot/buildbot)。

* [TeamCity](https://www.jetbrains.com/teamcity/) 是 JetBrains' 的闭源
  CI 服务器，它需要一个许可证才可以使用。

## Jenkins CI 相关的资源
* [用 Jenkins 为 Django 项目添加一个持续集成服务](https://medium.com/@mondaini/assembling-a-continuous-integration-service-for-a-django-project-on-jenkins-5f979d4c4184)
  说明了如何为一个含有 Jenkins 服务器的 Ubuntu 实例进行设置，并使用 Jenkins 服务器构建一个 [Django](/django.html) 项目。

* 我写的 [部署 Python web 应用](http://www.deploypython.com/) 一书中详细讲解了设置一个 Jenkins 项目（含有一个 WSGI 应用）并实现持续交付的每一个步骤。如果你对其它博客中列出的所有步骤还不够了解的话，可以去看看那本书。

* [将 Jenkins 设置为 Django 的持续集成服务器](http://michal.karzynski.pl/blog/2014/04/19/continuous-integration-server-for-django-using-jenkins/)
 是另外一篇不错的教程，它说明了如何将发送邮件通知集成到构建过程中。 

* 如果你在向你的 Jenkins 系统账户中添加用于连接另外一个服务器或 Git 仓库的 SSH 秘钥时遇到困难的话，
  [这篇让 Jenkins 和 Git 连接的博客](http://dcycleproject.org/blog/51/connecting-jenkins-and-git)
  会告诉你解决问题的步骤。

* [使用 Ansible 和 Jenkins 实现自动化服务器和部署](http://chromaticsites.com/blog/automated-servers-and-deployments-ansible-jenkins)。
  
* [在 Docker 容器中运行 Jenkins](http://www.catosplace.net/blog/2015/02/11/running-jenkins-in-docker-containers/)
  是一个简短的教程说明了如何在 Docker hub 中使用官方的 
  [Jenkins 容器](https://registry.hub.docker.com/_/jenkins/)。

* [保护 Jenkins 的安全](https://wiki.jenkins-ci.org/display/JENKINS/Securing+Jenkins)
  是 Jenkins 安全的登录页面。如果你正在部署你自己的实例，你需要给服务器加锁防止未授权的用户访问。

* [我们可以使用 Jenkins 做到吗？](http://engineering.simondata.com/can-we-use-jenkins-for-that)
  看看一个团队如何做到将 Jenkins 用于除了典型的持续集成之外的其它情形——他们也将它作为管理员接口、定时任务、数据分析细流水线以及长时间运行的脚本来使用。

## 通用持续继承相关资源
* [持续集成是什么？](http://martinfowler.com/articles/continuousIntegration.html)
  是由 Martin Fowler 写的经典文章，详细讲解了 CI 背后的概念以及实现的方式。

* [给务实的人准备的持续部署](http://www.airpair.com/continuous-deployment/posts/continuous-deployment-for-practical-people)
  不是专门针对 Python 的，但是它值得一读。

* [持续集成和交付（插图）](http://bitcubby.com/continuous-integration-delivery-illustrated/)
  使用清晰的绘图说明了持续集成和交付在用于测试和数据管理时是如何工作的。

* [新手深入学习持续集成](http://www.rackspace.com/blog/diving-into-continuous-integration-as-a-newbie/)
  是一个在 Rackspace 的实习生对她是如何学习 CI 的回顾。

* [StackShare 的持续集成标签](http://stackshare.io/continuous-integration) 
  列出了大量根据用户投票大致排名的托管 CI 服务。

* [持续集成最佳实践](http://buildoutcoredev.readthedocs.org/en/latest/continous-integration.html)
  包含了代码审查、合并测试以及恢复到之前版本的建议。

* [使用 Ansible、Docker 和 Teamcity 部署到 AWS](http://blog.bwhaley.com/deploying-to-aws-using-ansible-docker-and-teamcity)
  是一个例子，讲述了一种将 Teamcity CI 服务器用于自动部署的潜在方法。

* [集成测试为何重要](https://blog.codeship.com/continuous-integration-important/)
  从更高的层面说明了在一个集团中如何使用 CI 构建起开发者与开发者之间、开发者与非技术人员之间的信任。这篇文章同时也讨论了设置可靠 CI 的任务，如测试环境、[集成测试](/integration-testing.html) 以及 CI 结果的可见性。

