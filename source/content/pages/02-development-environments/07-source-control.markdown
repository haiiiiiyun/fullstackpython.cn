title: 源码控制
category: page
slug: source-control
sortorder: 0708
toc: False
sidebartitle: 源码控制
meta: 源码控制版本，并且可以在编程问题发生时恢复备份代码。快来 Full Stack Python 学习更多有关源码控制的知识吧。


# 源码控制
源码控制，也叫做*版本控制*，用于保存软件代码文件以及针对这些文件的每次变动的详细历史。

## 为何源码控制是有必要的？
版本控制系统允许开发者们修改代码，而不用担心某些情况下把事情彻底搞砸。不想要的变动可以轻松地回滚到之前的代码版本。

版本控制也使得团队软件开发更加轻松。一个开发者可以通过 [diff](http://en.wikipedia.org/wiki/Diff) 命令按行查看代码的变更，然后将合适的代码合并到主代码分支中，这样就可以将他的代码修改和其他开发者的代码合并了。

版本控制对于所有的软件项目来说都是必要的，不管开发时间、代码库大小或者使用的编程语言。每个项目都应当立即使用一个版本控制系统，例如 Git 或者 Mercurial。

## 开发期间使用源码控制
在开发期间拉取代码是源码控制系统适应开发进度的一种潜在方法。

<img src="/img/app-source-control.png" width="100%" class="technical-diagram" alt="App deployment uses a server to pull from the source control system.">

需要留意的是，一些开发者推荐在部署流水线中给源码打包并部署，并且永远不要让生产环境和源码控制系统直接接触。然而，对于小规模的软件开发，通常最简单的做法就是在你开始的时候直接从源码中拉取，而不用纠结如何将 Python 代码打包到系统安装包中。

## 源码控制项目
在过去的几十年里，人们创造了无数款源码控制系统。过去，专有的源码控制软件提供的功能都是为大型开发团队和特定项目流程定制的。然而，如今开源的源码控制系统正用在现存的最大并且最复杂的软件项目中。在今天的 Python 开发世界，没有理由去使用任何除了开源的源码版本控制系统了。两个主要的选择是：

* [Git](http://git-scm.com/) 是免费并且开源的分布式版本控制系统。

* [Mercurial](http://mercurial.selenic.com/) 和 Git 类似，也是一款免费开源的分布式版本控制系统。

## 源码控制托管服务
你可以在你的服务器上下载并运行 Git 和 Mercurial。 然而，开始使用一个托管的版本控制服务也是非常简单又便宜的。如果以后你的需求改变了，你可以通过移动你的仓库来从服务商那儿转移走。几个值得推荐的版本控制托管服务商有：

* [GitLab](https://about.gitlab.com/) 同时提供了针对个人的开源软件托管服务，以及需要额外托管支持的 [付费](https://about.gitlab.com/pricing/) 商业服务。

* [GitHub](https://github.com/) 为 Git 提供了免费的开源仓库以及付费的私有仓库。

* [BitBucket](https://bitbucket.org/) 也有支持 Git 和 Mercurial 的免费开源项目仓库，但是还支持最多 5 个用户的私有仓库。超过 5 个用户时，如果需要私有仓库托管服务就需要支付一定的费用了。

## 源码控制资料
* [暂存服务器，源码控制和部署工作流程，以及其它一些没人会教你的东西](http://www.kalzumeus.com/2010/12/12/staging-servers-source-control-deploy-workflows-and-other-stuff-nobody-teaches-you/) 
  是由 Patrick McKenzie 编写，是对为何你需要源码控制的全面概述。

* [版本控制最佳实践](https://blog.rainforestqa.com/2014-05-28-version-control-best-practices/)
  是一篇非常不错的文章，说明了如何使用版本控制系统。这篇文章是正在由 [Rainforest](https://www.rainforestqa.com/) 中的许多人参与编写的部署指南中的一部分。

* 这篇
  [版本控制发展史中的 10 件惊人的事情](http://www.flourish.org/2011/12/astonishments-ten-in-the-history-of-version-control/) 是一篇让人轻松的指南，它提供了一个有趣的途径来学习过去几十年中版本控制系统是如何发展的。

* [版本控制入门](http://betterexplained.com/articles/a-visual-guide-to-version-control/) 
  是一篇含有真实例子的详细文章，它说明了版本控制系统为何在软件开发中很有必要。

* [版本控制介绍](http://guides.beanstalkapp.com/version-control/intro-to-version-control.html) 
 展现了版本控制系统背后的概念。

* [什么是版本控制？为何它对于尽职审查非常重要？](http://oss-watch.ac.uk/resources/versioncontrol) 
  解释了版本控制系统的优势和必要性。

* [关于版本控制](http://git-scm.com/book/en/Getting-Started-About-Version-Control) 
回顾了分布式版本控制系统的基础知识。


## Git 相关资料
* [Pro Git](http://git-scm.com/book) 是一本开源的书籍，介绍了使用版本控制系统所有方面的知识。

* [600 字介绍 Git](http://maryrosecook.com/blog/post/git-in-six-hundred-words)
  是一篇解释 Git 基础概念的清晰又简明的文章。

* [Git 黑客指南](http://wildlyinaccurate.com/a-hackers-guide-to-git) 包含了基础和高级的 Git 命令，同时解释了每一步的操作含义。

* [像 Git 一样思考](http://think-like-a-git.net/) 是另外一篇介绍文章，它更多聚焦在图论和 Git 背后的概念性的思想，从而帮助读者理解在他们使用 Git 命令时究竟发生了什么。

* [Git 实践介绍](http://mrchlblng.me/2014/09/practical-git-introduction/)
  内容正如标题所描述的那样。这是一篇非常好的指南，提供了大量的代码片段来让你快速上手 Git。

* [Git 由内到外](https://codewords.recurse.com/issues/two/git-from-the-inside-out)
  通过一些 Git 命令样例展示了基于图的数据结构是如何产生某些行为的。在你已经掌握了 Git 的基础知识后，并且希望能深入 Git 的话，强烈推荐阅读这篇文章。

* [git 就绪](http://gitready.com/) 有一个非常不错的针对初级学者、中级学者和高级 Git 用例的博客合集。

* [git 流程](http://nvie.com/posts/a-successful-git-branching-model/) 详细描述了针对小团队的 Git 分支模型。

* [GitHub 流程](http://scottchacon.com/2011/08/31/github-flow.html) 基于“git 流程”构建，重温了一些使用 GitHub 的问题，并且给出了一些针对那些问题的解决方案。

* [Git可行的工作流程](http://blog.endpoint.com/2014/05/git-workflows-that-work.html)
  是一篇非常有帮助并且带有图表的文章，它说明了团队如何才能创建一个对他们开发进度有帮助的 Git 流程。

* "[我们的 Git 工作流程](http://www.braintreepaymentsolutions.com/devblog/our-git-workflow)" 是 Braintree 编写的，回顾了这家会计公司如何使用 Git 进行开发并合并源码的。

* [借助 Git 进行代码审查](https://robots.thoughtbot.com/code-sleuthing-with-git)
  说明了当开发出现问题后，该如何审查过去的变更，从而找出问题。

##源码控制学习清单
1. 选择一个版本控制系统。在这里推荐使用 Git 的原因在于网上有大量帮助新用户和高级用户的教程。

1. 学习一些基本的版本控制用法，比如提交变更、回滚到之前的文件版本以及搜索在开发过程中何时变动了代码行数。

1. 确保你的源码备份到了一个中心仓库。中心仓库是非常重要的，不仅是为了防止你本地的开发版本受损，而且也是为了开发进度。

1. 需要三步来集成源码控制到开发过程中。首先，在开发期间，从版本控制系统中拉取项目源码。第二，使用 webhooks 或者轮询仓库的方式在代码修改时启动部署。第三，当开发出现问题时，确保你能够回滚到之前的版本。

