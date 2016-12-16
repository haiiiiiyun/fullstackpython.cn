title: 配置管理
category: page
slug: configuration-management
sortorder: 0712
toc: False
sidebartitle: 配置管理
meta: 配置管理工具可以自动完成应用部署和环境设置。
translators: http://blog.chriscabin.com
updated: 2016-07-21 08:00


# 配置管理
配置管理涉及的内容包括如何将服务器从一个现有状态修改为期望的状态以及如何自动化部署应用。

## 配置管理工具
很多现有的工具都能以可控的方式修改服务器状态，包括
[Puppet](http://puppetlabs.com/puppet/what-is-puppet), 
[Chef](http://www.getchef.com/chef/)、
[SaltStack](http://www.saltstack.com/)、和 Ansible。其中Puppet 和 Chef 是用 Ruby 编写的，而 SaltStack 和Ansible 则是用 Python 编写的。

## 特别任务
诸如 Chef、Puppet、Ansible 和 SaltStack 等一些配置工具对于执行需要交互响应的特别任务并不是很有用。
[Fabric](http://docs.fabfile.org/en/1.8/) 和 
[Invoke](http://docs.pyinvoke.org/en/latest/) 则适用于交互式操作，比如使用 Django manage.py 脚本查询数据库。

## 配置管理工具对比
* [从 Puppet 迁移：选择 SaltStack 还是 Ansible？](http://ryandlane.com/blog/2014/08/04/moving-away-from-puppet-saltstack-or-ansible/)
  是一篇公然带有偏见的文章，但它详细讲解了为什么在某些情形下应该选择 SaltStack 而非 Ansible。
  
* [Ansible 对比 Shell 脚本](http://devopsu.com/blog/ansible-vs-shell-scripts/)
  提出了一些有关为何配置管理工具比老旧脆弱的 shell 脚本更好的观点。

* [Ansible 对比 Chef](http://tjheeta.github.io/2015/04/15/ansible-vs-chef/)
  是 Ansible 和 Chef 这两款配置管理工具的对比。

* 这篇文章 [Ansible 和 Salt: 详细比较](http://missingm.co/2013/06/ansible-and-salt-a-detailed-comparison/)
  说明了这两款基于 Python 的工具之间的区别。

## Ansible
[Ansible](http://www.ansibleworks.com/) 一款使用 Python 构建的开源配置管理工具和应用部署工具。

### Ansible 相关资源
* [一个 Ansible 教程](https://serversforhackers.com/editions/2014/08/26/getting-started-with-ansible/)
  是一个非常详细的教程，介绍了如何使用 Ansible 设置服务器。

* [带有 Twilio 短消息服务的 Ansible 文本消息通知](https://www.twilio.com/blog/2014/05/ansible-text-messages-notifications-with-twilio-sms.html)
  是我的一篇博客，它有一个详细的例子演示了如何在核心的 Ansible 1.6+ 版本中使用 Twilio 模块。

* [Python 用于配置管理（使用Ansible）的幻灯片](http://www.insom.me.uk/post/pycon-talk.html) ，来自 2013 年在 UK 举办的 PyCon 会议。

* [使用 Ansible 的第一步](http://labs.qandidate.com/blog/2013/11/15/first-steps-with-ansible/)。

* [Red Badger 网站中关于 Ansible 的文章](http://red-badger.com/blog/2013/06/29/ansible/)。

* [入门 Ansible](http://lowendbox.com/blog/getting-started-with-ansible/)。

* [Ansible 介绍](https://davidwinter.me/introduction-to-ansible/)
  是一篇介绍 Asible 工具使用基础的教程。

* [Ansible 和 Linode](http://softwareas.com/ansible-and-linode-what-i-learned-about-controlling-linodes-from-ansible)。

* [使用 Ansible 和 Duo Security 实现多步认证](http://jlafon.io/ansible-duo-security.html)。

* [在遗留项目中引入 Ansible](http://benlopatin.com/getting-started-with-ansible/)。

* [Ansible 后期安装步骤](http://devopsu.com/guides/ansible-post-install.html) 。

* [在服务器上使用 Ansible 最初的五分（半）钟](http://lattejed.com/first-five-and-a-half-minutes-on-a-server-with-ansible) 。

* [Ansible 超级实用的 6 个实践经验](http://hakunin.com/six-ansible-practices)。

* [Shippable + Ansible + Docker + Loggly 用于绝妙部署](http://www.hiddentao.com/archives/2014/06/03/shippable-ansible-docker-loggly-for-awesome-deployments/)
  是一篇非常不错的文章，讲解了如何搭配使用 Docker 和 Ansible 以及一些其它的工具。

* [使用 Ansible 创建一个 Couchbase 集群](http://blog.couchbase.com/create-couchbase-cluster-with-ansible)。

* [幂等性、收敛性和其它一些我们经常使用的愚蠢单词](https://groups.google.com/forum/#!msg/Ansible-project/WpRblldA2PQ/lYDpFjBXDlsJ)。

* [如何为 Ansible Galaxy 写一个 Ansible 模块（Role）？](http://probablyfine.co.uk/2014/03/27/how-to-write-an-ansible-role-for-ansible-galaxy/)

* [使用  Jenkins、Docker 和 Ansible 进行测试](http://blog.mist.io/post/82383668190/move-fast-and-dont-break-things-testing-with)。


## 配置管理学习清单
1. 学习有关配置管理在部署自动化和“基础设施即代码”部分的内容。

1. 选择一款配置管理工具并坚持使用它。我推荐使用 Ansible，因为它是到目前为止最容易学习使用的工具。

1. 阅读你的配置管理工具的文档，并且在有必要时阅读它的源代码。

1. 为你的项目实现配置管理和部署自动化。注意这是你在整个学习清单中最耗时的步骤，但是当你每次部署项目时，你都会得到相应的汇报。

1. 将自动化部署工具添加到你现有的部署进程中。

