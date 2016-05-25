title: 企业 Python
category: page
slug: enterprise-python
sortorder: 0105
toc: False
sidebartitle: 企业 Python
meta: 在世界各地的大型机构中 Python 被广泛用于构建企业应用。
translator: haiiiiiyun.github.io
updated: 2016-05-25 11:05


# 企业 Python
关于 Python 等动态类型语言的一个错误观念认为它们用于构建企业级应用还不太可靠。然而，几乎所有的商业和政府机构都已经或多或少使用 Python 了，无论是作为不同的应用程序之间的粘合代码还是构建应用程序本身。

## 什么是企业软件？
企业软件是为机构的需求而非个人的需要创建的。为企业编写的软件通常需要与历史遗留系统，例如现有的数据库和单机应用程序进行整合。通常也需与 [轻量级目录访问协议 (LDAP)](http://en.wikipedia.org/wiki/Lightweight_Directory_Access_Protocol) 和 [活动目录 (AD)](https://msdn.microsoft.com/en-us/library/aa746492%28v=vs.85%29.aspx) 这样的认证系统整合。 

机构开发企业软件，包含大量的定制需求以适应其运营模式的具体需要。 因此，由于组织内部不同派系之间为争取软件能优先解决其各自的需求而罔顾他人的斗争，往往会导致软件开发过程变得异常复杂。

因企业软件建设过程涉及到许多利益相关者而产生的复杂局面，导致了大量的预算以及由机构中非技术人员执行的过度审查。而这些非技术人员通常在编程语言和框架的选择上妄加评断--而他们是不应该做出技术设计决策的。

## 为什么企业环境中存在对 Python 的误解？
传统大型机构使用静态类型语言如 C++、 .NET 和 Java 构建企业软件。上世纪80年代和90年代的大公司，如微软、Sun 和 甲骨文将这些语言标榜为”企业级“语言进行市场销售。其直接后果是，其它语言受到了冷落，并被看作不适应 CIO 的艰难技术环境。除了 Java、C++ 和 .NET，其它语言都被认为是有风险的，因而不值得投资使用。

此外， 在 20 世纪 90 年代， ”脚本语言“如 Python、Perl 和 Ruby 都还不够强大， 因为他们的核心标准库都仍处在开发阶段。像 [Django](/django.html)、[Flask](/flask.html) 以及 Rails (Ruby 语言) 这样的框架还没有产生。 那时的网络还刚刚开始，大多数企业应用还只是 Windows 系统上的桌面应用程序。 而 Python 根本不适合用于那样的环境。

## 为什么说 Python 现在适合于构建企业级软件？
从本世纪初到现在，许多动态类型语言及其生态系统有了很大的发展，而且在某些方面往往超越了其它生态系统。Python、 Ruby 以及其它之前被冷落的语言现在有了更广阔并且维护良好的开源生态系统，它们受到独立开发者和大公司的支持，包括微软、IBM、谷歌、Facebook、Dropbox、Twilio等等。

Python的开源库，特别是针对[Web开发](/web-frameworks.html)和数据分析的那些代码，对于任何语言来说，都是维护良好功能完备的典范。

同时，一些传统的企业软件开发语言如 Java 因受主要企业支持者投资不足影响，已经衰落了。当 [Oracle 于2009 年收购 Sun](http://www.oracle.com/us/corporate/press/018363) 时，在 Java 中增加新的语言特性以升级到 Java 7 的计划已被拖了很多一段时间。Oracle 还在 [Java 安装包中捆绑了不需要的广告软件](http://www.engadget.com/2015/03/06/java-adware-mac/)，而 Python 社区绝不会容忍这种情况发生，因为这门语言是开源的，并不受某一公司控制。

其他的生态系统，如微软的 .NET 平台则发展的较好。微软在整个新世纪的早期阶段对 .NET 平台进行了持继投资以促进及发展。

然而，微软的企业产品，它们的应用程序服务器和相关软件往往有昂贵的许可费用。此外，微软也是开源运动的主要支持者，
[尤其对于 Python 来说](http://www.hanselman.com/blog/OneOfMicrosoftsBestKeptSecretsPythonToolsForVisualStudioPTVS.aspx)，他们的
[Visual Studio Python 工具集](https://www.visualstudio.com/en-us/features/python-vs.aspx) 提供了一流的 [开发环境](/development-environments.html)。


最终的结果是企业软件开发在过去的几十年中发生了翻天覆地的变化。CIO和技术管理人员，如果想继续为他们的业务侧客户提供商业价值的话，不再能忽视 Python 及伟大的开源社区在企业软件开发领域所取得的进展了。


## 开源企业 Python 项目
* 由美国政府机构 [消费者金融保护局](http://www.consumerfinance.gov/) (CFPB)主导的 [Collab](https://github.com/cfpb/collab) 是一个为大型机构服务的企业内联网及协作平台。该项目目前已投入运行，并被成千上万的 CFPB 员工使用着。

* [Pants](https://github.com/twitter/pants) 是一个针对大型机构软件项目的构建系统，这些项目通常包含许多个由不同的编程语言编写的子项目 。

## 企业 Python 软件开发资源
* CIO 期刊上有很多篇靠谱的揭密文章，如这篇 [Python 企业开发概述](http://www.cio.com/article/2437137/developer/you-used-python-to-write-what-.html) 和这篇 [为什么动态语言在企业开发中占有越来越多的份额](http://www.cio.com/article/2431212/developer/dynamic-languages--not-just-for-scripting-any-more.html)。

* JavaWorld 上有一篇很有趣的文章叫 [Python 进军企业软件开发之路](http://www.javaworld.com/article/2078655/scripting-jvm-languages/python-coming-to-the-enterprise--like-it-or-not.html)。

* 我在 2014 年 DjangoCon 上讲了 [如何用 Django 解决企业的5个问题](https://www.youtube.com/watch?v=aMtiCX38w20)，内容覆盖如何在大型机构中使用 Python 和 Django。

* 这篇 [StackExchange 答案](http://programmers.stackexchange.com/questions/141411/what-is-enterprise-software-exactly) 详细阐述了企业软件与传统软件的区别。

* 这篇 Reddit 上的 Python 主题文章 [企业中的 Python](https://www.reddit.com/r/Python/comments/3myppd/everyone_who_encounters_it_seems_to_love_python/) 值得一读，里面有针对在企业环境中 Python 对比 Java 和 .NET 的更广泛观点。
