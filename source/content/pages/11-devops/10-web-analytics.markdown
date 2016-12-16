title: Web 分析
category: page
slug: web-analytics
sortorder: 0716
toc: False
sidebartitle: Web 分析
meta: Web 分析工具会收集来自访问者的数据，并将数据采用可视化方式呈现出来，从而帮助开发者们更好地为用户服务。快来 Full Stack Python 学习更多有关 web 分析的知识吧。
translators: blog.chriscabin.com
updated: 2016-07-25 16:30


# Web 分析
Web 分析涉及的内容有收集、处理和可视化 web 数据，从而以批判性思维看待用户是如何与 web 应用交互的。


## Web 分析为何重要？
用户客户端，特别是 web 浏览器，会在用户读取以及与 web 页面交互时产生非常重要的数据。
利用相关数据可以分析出用户是如何使用网站的以及他们停驻或离开的原因。
分析的关键概念是从你的用户那儿*学习*，以便于你能改进 web 应用从而更好地符合他们的需求。


## Web 分析概念
很容易会对大量的分析服务和收集到的无数类型的数据点感到不知所措。当你刚开始时，仅专注于少量的指标即可。
随着你的应用规模逐渐扩展，你会更加理解你的用户，然后就可以使用高级的可视化工具，如热图，和行为漏斗（action funnels），来增加额外的分析服务，从而获取更多分析用户行为的数据。


### 用户漏斗
如果你的应用程序是用来出售产品或服务的，你最终可以构建一个 [用户漏斗](http://moz.com/blog/building-your-marketing-funnel-with-google-analytics)（通常称为“营销漏斗”，即之前的用户变成后来的消费者）来更好地理解为何人们会购买或者不买你正在出售的东西。使用一个漏斗，你可以明显地看到访客在采取行动前，比如购买你的服务，就离开你的应用程序的急剧下降点在何处。


## 开源 web 分析项目
* [Piwik](http://piwik.org/) 是一个你可以自己托管的 web 分析平台。如果你不能使用 Google 分析器或者想要自定义你的 web 分析平台，Piwik 即是不二之选。

* [开源 Web 分析](http://www.openwebanalytics.com/) 是另外一款自托管的平台，它通过集成了一个 JavaScript 片段代码来追踪用户与页面的交互行为。


## 托管的 web 分析服务
* [Google 分析器](http://www.google.com/analytics/) 是一款广泛用于网站流量分析的免费工具。

* [Clicky](http://clicky.com/) 与 Google 分析器的实时操作面板相比，提供了实时分析功能。

* [MixPanel](https://mixpanel.com/) 的分析平台侧重于移动端和营销漏斗指标。开发者可以将收集数据点的代码构建到服务器端或者客户端。MixPanel 会收集数据，然后根据依据数据产生指标并可视化数据。 

* [KISSmetrics](https://www.kissmetrics.com/) 分析会提供谁正在访问网站以及他们正在网站做什么的信息。

* [Heap](https://heapanalytics.com/) 是最近成立的分析服务平台，提供了免费的入门级别服务。

* [CrazyEgg](http://www.crazyegg.com/) 是一款基于鼠标动作生成的热图来理解用户在使用网站时的焦点所在的工具。


## 针对 Python 的 web 分析资源
* [使用 Flask 构建一款分析应用](http://charlesleifer.com/blog/saturday-morning-hacks-building-an-analytics-app-with-flask/)
  详细讲解了如何使用你自己的 Flask 应用收集并分析网页。

* [Pandas 和 Google 分析器](http://blog.yhathq.com/posts/pandas-google-analytics.html)
  说明了如何使用 pandas 来分析使用 Google 分析器 API 获得的数据，从而执行工具本身不支持的计算功能。
  
* [在 Excel 中构建你自己的 Google 分析器操作面板](http://blog.zoomeranalytics.com/google-analytics/)
  说明了如何通过 Google 的 web API 和 Python 库提取出 Google 分析器的数据，从而能够在其它工具（如 Excel）中使用数据。

## 通用 web 分析资源
* [给开发者的 Googel 分析器](http://blog.arkency.com/2012/12/google-analytics-for-developers/) 。

* 这篇入门指南 
  [隐藏在 web 分析器背后的数学和统计学](http://www.seotakeaways.com/beginners-guide-maths-stats-web-analytics/)
  提供了一些用于理解和推断 web 流量的知识。

* [给开发者的分析器入门指导](https://hacks.mozilla.org/2015/03/an-analytics-primer-for-developers/)
  ，由 Mozilla 提供，说明了应该追踪什么，如何选择分析器平台以及如何利用 JavaScript 进行异步分析。

* 这篇文章告诉你如何判断一个给定的指标是 [“无意义的”或者有用的](http://fizzle.co/sparkline/vanity-vs-actionable-metrics)。


## Web 分析学习清单
1. 在你的应用中添加 Googel 分析器或者 Piwik。二者都是免费的，但相对来说 Piwik 不如 Google 分析器强大，你可以自托管应用，这在许多环境中是唯一的选项。

1. 批判性地对待各种因素会使你的应用变成功。这些因素的不同之处取决于它是否是一款 [企业](/enterprise-python.html) 内部应用、一个电子商务网站或者是一款以信息为基础的应用。

1. 添加那些基于驱动你应用成功的因素而产生的 web 流量指标。你可以使用一些自定义的代码或者一个托管 web 分析器服务来添加这些指标。

1. 持续不断地评估你挑选的那些还是不是仍然能够定义你的应用成功的合适指标。如有必要，就改善使用 web 分析工具产生的指标。
