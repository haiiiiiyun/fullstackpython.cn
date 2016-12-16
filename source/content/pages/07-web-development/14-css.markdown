title: 级联样式表
category: page
slug: cascading-style-sheets
sortorder: 0411
toc: False
sidebartitle: 级联样式表 (CSS)
meta: 到 Full Stack Python 上学习如何使用级联样式表 (CSS) 来设计你的 Web 应用用户界面。
authors: haiiiiiyun.github.io
updated: 2016-06-19 14:57


# 级联样式表 (CSS)

级联样式表 (CSS) 文件包含了浏览器如何显示和布局 HTML 内容的规则。

## 为什么说 CSS 是必需的？
CSS 将 HTML 文件内容与其如何显示进行了分离。将内容与其应该如何呈现的规则分离的重要性主要在于：可以在多个页面中更加容易复用这些规则。相比于嵌在 HTML 文件中的样式内容，大型项目中使用 CSS 文件还更易于维护。

## CSS 是怎样从 Web 服务器上获取的？

由 Web 服务器发送的 HTML 文件中包含有指向 CSS 文件（用于呈现内容）的引用地址。浏览器获取到 HTML 文件后，再请求 CSS 文件，如下面的截图所示，该图是从 Chrome Web 开发者工具中的网络流量标签页截取的。

<img src="/img/css-chrome-dev-tools.jpg" width="100%" alt="Google Chrome Web 开发者工具显示了 CSS 是如何与 HTML 内容分离的。" class="technical-diagram" />

发送了一个对 fsp.css 文件的请求是因为 Full Stack Python 的 HTML 文件中包含了一个到 ``theme/css/fsp.css`` 的引用，如下面的显示源代码截图所示。

<img src="/img/fsp-css-source.jpg" width="100%" alt="View source screenshot for the fsp.css file in index.html." class="technical-diagram" />


## CSS 预处理器
CSS 预处理器将处理语言编译成纯 CSS 代码。CSS 处理语言通过增设变量、mixin、函数等语法结构来减少代码的重复度。有了这些额外的语法，使得设计人员使用这些基本的编程结构来编写可维护的前端代码变得可能。

* [Sass](http://sass-lang.com/) 是一款目前在设计界备受青睐的预处理器。Sass 具有很多高级的语言特性，因此被认为是功能最强大的 CSS 预处理器。

* [LESS](http://lesscss.org/) 是一款与 Sass 不分上下的预处理器，由于 [Bootstrap 框架](http://getbootstrap.com/) 是用 LESS 写的，LESS 现在变得越来越受欢迎了。
* [Stylus](http://learnboost.github.io/stylus/) 经常被认为是排名第三的最受欢迎的 CSS 预处理语言。


### CSS 预处理器资源
* 《Advanced Guide to HTML and CSS》这本书中有一章是专门讲 [预处理器](http://learn.shayhowe.com/advanced-html-css/preprocessors)的，写的很好。

* [Sass 对比 LESS](http://css-tricks.com/sass-vs-less/) 先是对应该选用哪个框架这个问题给出了个精简的回答，然后为那些想了解细节的用户给出来一份详实的答案。

* [如何选择一个合适的 CSS 预处理器](http://blog.teamtreehouse.com/how-to-choose-the-right-css-preprocessor) 对 Sass、LESS 和 Stylus 进行了对比。

* [对 CSS 预处理器的思考](http://css-tricks.com/musings-on-preprocessing/) 这篇文章中包含了一些很有用的建议，内容包括从如何在团队环境中使用预处理器到你该用什么应用程序来辅助你的工作流等等不一而足。

## CSS 框架
CSS 框架为 Web 应用的设计提供架构和样板文件。

* [Bootstrap](http://getbootstrap.com/)

* [Foundation](http://foundation.zurb.com/)

* [Gumby](http://gumbyframework.com/)

* [Compass](http://compass-style.org/)

* [Profound Grid](http://www.profoundgrid.com/)

* [Skeleton](http://www.getskeleton.com/)

* [HTML5 Boilerplate](http://html5boilerplate.com/)


## CSS 资源
* [前端开发书签](https://github.com/dypsilon/frontend-dev-bookmarks) 是一个有关前端知识的最有价值的资料库之一，里面即包含 CSS 也包含 Javascript。

* [CSS 复习摘记](https://github.com/vasanthk/css-refresher-notes) 对于之前一直是零星学习 CSS知识，现在又想填充知识空白的你来说相当有帮助。

* [Mozilla 开发者网络中的 CSS 页面](https://developer.mozilla.org/en-US/docs/Web/CSS) 上包含有 CSS 知识的丰富资源、教程和示例。

* [CSS 定位 101](http://alistapart.com/article/css-positioning-101) 这份详细指南讲解了如何用 CSS 进行正确的元素定位。

* [CSS3 小抄](http://media.smashingmagazine.com/wp-content/uploads/images/css3-cheat-sheet/css3-cheat-sheet.pdf)。

* [学习 CSS 布局](http://learnlayout.com/toc.html) 这篇简单的指南将 CSS 布局相关主题分成几个章节来讲解，因此你可以按步每次学一部分内容。

* [Google Web 基础课程](https://developers.google.com/web/fundamentals/) 讲解了如何创建响应式的设计和高性能的网站。

* [CSS 性能调优](http://programming.oreilly.com/2014/04/tailoring-css-for-performance.html) 是一篇很有意思的文章，因为很多开发人员不会考虑 CSS 的复杂性对浏览器渲染时间的影响。

* [我能用 ...](http://caniuse.com/) 是一个兼容表格，显示了哪个版本的浏览器实现了哪些特定的 CSS 功能。


## CSS 学习清单
1. 创建一个只含基本元素的简单 HTML 文件。使用 ``python -m SimpleHTTPServer`` 命令来开启服务端进程。在 HTML 文件的 ``<head>`` 区域中创建一个 ``<style></style>``。 在 style 元素中通过试验 CSS 来改变页面的外观。

1. 研究 Bootstrap 或 Foundation 等前端框架，并将框架集成到 HTML 页面中。

1. 练习该框架的网格系统、样式选项和定制功能，以便熟悉如何使用该框架。

1. 将该框架应用到你的 Web 应用中并调整设计，直到实现比通用 HTML 更好的效果。
