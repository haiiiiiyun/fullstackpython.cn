title: Web 应用安全
category: page
slug: web-application-security
sortorder: 0415
toc: False
sidebartitle: Web 应用安全
meta: Web 应用会受到恶意份子的各种攻击。到 Full Stack Python 上学习有关安全措施的知识。
updated: 2016-06-29 12:48


# Web 应用安全
构建 Web 应用的每个阶段都必须要考虑网络安全问题。但是，本节包含的主题内容，如跨站脚本 (XSS)， SQL 注入， 跨站请求伪造 (CSRF) 和公钥/私钥对的使用等，都值得我们特别关注。

## 网络安全开源项目
* [Bro](http://www.bro.org/) 是一个网络安全及流量监测器。

* [快速 NIX 安全脚本](https://github.com/marshyski/quick-secure) 能用于提升 Linux 发行版的安全性。

* [lynis](https://github.com/CISOfy/lynis) 是一个非常好的安全审计工具，它能以 shell 脚本的形式在 Linux 系统上运行，以便找出系统漏洞加以修复，从而避免被恶意份子利用。

## HTTPS 资源
* [HTTPS 到底如何工作？](http://robertheaton.com/2014/03/27/how-does-https-actually-work/) 是一篇有关该协议的概述性文章，包含认证、签名、签署等相关主题内容。

* 这些 [介绍 HTTPS](https://18f.gsa.gov/2015/07/16/introduction-to-https-webinar/) 的视频讲解了什么是 HTTPS 及如何实现它。

* 有人问到 [TLS 和 SSL 之间有什么区别？](http://security.stackexchange.com/questions/5126/whats-the-difference-between-ssl-tls-and-https)，上面的答案解释到：TLS 是 SSL 的更新版本，应该使用 TLS，因为 3.0 版本以下的所有 SSL 都是不安全的。

* 如果你想知道 SSL/TLS 等这些缩写词到底是什么意思的，可以看看 [安全性/服务端 TLS 指南](https://wiki.mozilla.org/Security/Server_Side_TLS)，Mozilla 就是按此部署它的服务器的。

* 如果你的用户需要向你的网站提交敏感信息，你就需要使用 SSL/TLS。TLS 之前的任何版本现在都是不安全的了。阅读这篇 [实用指南](http://wingolog.org/archives/2014/10/17/ffs-ssl) 来了解有关该主题的详细知识。

* [SSL 的糟糕状态](https://hynek.me/talks/tls/) 详述了 SSL/TLS 的演化历史。 这两者之间有着非常重要的差别，Hynek 还讲解了为何必须要用 TLS的原因。该文还促使人们基于 Python 3 中的升级内容来对 Python 2.7.9 中的 SSL 进行了改进，并且记录在 [Python 中的 SSL 并不那么糟糕](https://developer.rackspace.com/blog/the-not-so-sorry-state-of-ssl-in-python/) 这篇文章中。 

* [HTTPS 如何提升连接的安全性](http://blog.hartleybrody.com/https-certificates/) 是一篇讲解 HTTPS 能够保障什么和不能保障什么的指南性文章。

* [何时及如何部署 HTTPS](http://erik.io/blog/2013/06/08/a-basic-guide-to-when-and-how-to-deploy-https/)。

* [HTTPS 连接的最开始几微秒](http://www.moserware.com/2009/06/first-few-milliseconds-of-https.html) 提供了 SSL 的握手过程的详细描述。浏览器是基于 [RFC 2818](http://tools.ietf.org/html/rfc2818) 标准来实现该过程的。

* [Qualy SSL 服务器测试](https://www.ssllabs.com/ssltest/) 能用于测定你的服务器 HTTPS 连接纰漏。 进行测试后，再阅读这篇文章 [在 Qualy SSL 实验测试中获取 A+ 成绩](https://sethvargo.com/getting-an-a-plus-on-qualys-ssl-labs-tester/) 来提升你的安全状况。
  

## 通用网络安全资源
* 开放 Web 应用安全项目 (OWASP) 上有一份有关 [各种安全性主题的备忘单](https://www.owasp.org/index.php/Cheat_Sheets)。

* 该页上包含了一份 [精心整理的安全性相关的资料列表](http://dfir.org/?q=node/8/)，内容从初级到高级主题，应有尽有。

* Reddit 的 [/r/netsec](http://www.reddit.com/r/netsec/) 页是一个了解网络和应用安全的好地方。

* [黑客工具库](http://gexos.github.io/Hacking-Tools-Repository/) 是一份关于密码破解、扫描、嗅探和其它安生渗透测试工具的列表。

* [加固 Ubuntu 服务器的安全性](http://www.andrewault.net/2010/05/17/securing-an-ubuntu-server/)。

* [Ubuntu 的安全性](http://joshrendek.com/2013/01/securing-ubuntu/)。

* [来自 Apache 的安全建议](http://httpd.apache.org/docs/current/misc/security_tips.html)。

* [加固 Linux 服务器的安全性](http://spenserj.com/blog/2013/07/15/securing-a-linux-server/)。

* EFF 上有一篇关于 [如何进行有效的安全审计](https://www.eff.org/deeplinks/2014/11/what-makes-good-security-audit) 文章。讲得比较笼统，但是里面包含一些他们的有关安全审计重要性的思考。

* Ars Technica 的文章 [提升你的网站安全性](http://arstechnica.com/security/2013/02/securing-your-website-a-tough-job-but-someones-got-to-do-it/) 及 [如何设置一个安全的 Web 服务器：第 1 部分](http://arstechnica.com/gadgets/2012/11/how-to-set-up-a-safe-and-secure-web-server/) 和 [第 2 部分](http://arstechnica.com/information-technology/2012/11/securing-your-web-server-with-ssltls/)，对 HTTPS 和 SSL 作了讲解，你不需要额外的知识就能看懂。

* [Crypto 101](https://www.crypto101.io/) 是针对程序员的一门密码学入门课程。

* [深入分析 Amazon EC2 上的 SSH 攻击](http://getprismatic.com/story/1409447605839) 阐述了加固 Web 服务器的安全是多么的重要，特别当你的服务器所有的 IP 地址段经常被恶意份子扫描时。

* [云安全审计：挑战与新的解决方法](http://www.infoq.com/articles/cloud-security-auditing-challenges-and-emerging-approaches) 是一篇讲述伴随云部署而来的安全性审计问题的高度概括性文章。

* 想知道通常的缓冲区溢出攻击是怎样实现的吗？阅读这篇 [有关缓冲区溢出的文章](http://arstechnica.com/security/2015/08/how-security-flaws-work-the-buffer-overflow/)，里面以非专业的角度对这种攻击进行了讲解。

* [保护服务器的 7 个安全措施](https://www.digitalocean.com/community/tutorials/7-security-measures-to-protect-your-servers) 是一篇讲述如果配置服务器来提供基本安全的基础性概述文章。

* 如果你用 Linux 做开发的话，你应该阅读和遵照 [Linux 工作站安全](https://github.com/lfit/itpol/blob/master/linux-workstation-security.md) 文档，以确保你的代码和环境都没有受到危害。如果你用 Mac OS X 的话，阅读 [提升 Yosemite 安全性指南](https://github.com/drduh/OS-X-Yosemite-Security-and-Privacy-Guide)，里面讲解了该环境的安全问题。

* [TLS 和 Nginx Web 服务器加固](https://www.moses.io/2015/09/tls-and-server-hardening-post-nginx/) 讲述了 Nginx 服务器的一种安全配置方法。

* [时间漏洞攻击法](http://arstechnica.com/security/2015/10/new-attacks-on-network-time-protocol-can-defeat-https-and-create-chaos/) 能用于攻破特定配置条件下的 HTTPS。理解这些攻击原理对于确保用户连接的安全性是非常重要的。


## Web 安全学习清单
1. 阅读和了解那些经常会被恶意份子加以利用的主要 Web 应用安全漏洞。包括跨站请求伪造 (CSRF)、跨站脚本 (XSS)、SQL注入和会话劫持等。[OWASP 前 10 位 Web 应用漏洞列表](https://www.owasp.org/index.php/Top_10_2013-Top_10) 是了解这些主题概念信息的好地方。

1. 检查你所选的框架是如何妥善处理这些漏洞的。

1. 确保你的代码也使用了框架提供的漏洞处置技术。

1. 以攻击者的角度进行思考，并主动攻击自己的系统。如果你没有经验来攻破安全防线，可以考虑雇用一位认识的白帽黑客。一旦攻破了应用的安全防线，应报告应用中最易被利用的漏洞，并帮助实现针对这些漏洞的保护措施。

1. 认识到没有系统是完全安全的。但是，应用系统越流行，就越可能会成为攻击目标。应经常对你的 Web 应用的安生性进行重新评估。
