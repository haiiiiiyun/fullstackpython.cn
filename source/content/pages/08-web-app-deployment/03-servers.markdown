title: 服务器
category: page
slug: servers
sortorder: 0702
toc: False
sidebartitle: 服务器
meta: 运行 web 应用需要服务器。快来 Full Stack Python 学习更多关于配置服务器的知识吧。
translators: blog.chriscabin.com
updated: 2016-07-10 20:25


# 服务器
服务器是运行所有软件层的物理设施，这样你的 web 应用才能够响应诸如 web 浏览器这样的客户端请求。


## 为何需要服务器？
你的 web 应用必须在除了你的台式机或者笔记本以外的设备上运行。 除了安排的关机计划外，理想的服务器应当保证每周 7 天，每天 24 小时能够正常访问。这台托管了针对真实用户（相对于测试用户）的 web 应用的主机就是所谓的*生产*服务器。
生产服务器保存了真实的数据（同样相对测试数据），并且必须安全，能够拒绝非授权的访问。


## 裸机服务器
*裸机*是指购买真实的硬件，然后通过商业级别的因特网服务供应商（ISP）或者是
[连接服务器](http://webdesign.about.com/od/colocation/a/what_colocation.htm)
到其它服务器上的方式连接到因特网。选择一个“商业级别”的 ISP 是有必要的，因为多数住宅因特网服务协议明文禁止在它们的网络上运行 web 服务器。如果网站的访问流量较低，那或许可以；但如果你的网站服务流量很大，那将会引起一个 ISP 的过滤警告。

采用裸机方案可以提供最多的服务器配置控制权限，
通常可以在相同价格下拥有最高的性能。但它同样也是在前期需要投入最多资金以及后期需要付出最多的服务器日常维护成本的方案。 使用裸机服务器，后期的操作成本包括服务器供电以及修复服务器损坏的部件。你需要承担人工劳动力来配置硬件以及剩余的软件栈的费用。

你可以从供应商购买组装好的服务器硬件，或者是各种组件集合回来自己组装。你也可以从 Dell 或者 HP 购买预先配置好的服务器。 这些服务器比较小巧紧凑（称为“刀片”服务器）， 但是相应地，和你使用现成的部件组装成普通的计算机相比，这种服务器更加昂贵。


## 虚拟化服务器
虚拟私有服务器（VPS） 就是在一个更大的裸机服务器上进行分割。 诸如
[Xen](http://www.xen.org/) 和
[VMWare](http://www.vmware.com/virtualization/what-is-virtualization.html)
这样的虚拟化软件，允许像 [Linode](http://www.linode.com/) 和
[prgmr](http://prgmr.com/xen/) （以及许多其他的供应商） 这样的供应商把一个完整服务器的一部分能够像一个完全独立的服务器实例提供给用户。例如，一台拥有 8 核 Xeon 处理器和 16 GB 内存的服务器，可以分割成 8 片，每片都拥有等同的 1 核处理器和 2 GB 内存。

虚拟化服务器最大的缺点在于虚拟进程有一定的资源开销。此外，一些物理限制，如某个虚拟化实例对持久化存储设备繁重的 I/O 操作会给共享服务器上其它虚拟化实例带来性能上的瓶颈。应当根据你对服务请求的紧迫性以及后期维护的频率需求，如持久化存储设备的备份，来决定是否选择虚拟化服务器托管方案。

### 与虚拟化服务器有关的资源
* [选择低成本的 VPS](http://blog.redfern.me/choosing-a-low-cost-vps/)
  讨论了一些在你决定选择托管供应商之前应当权衡的因素。

* [如何用最出色的方式设置你的 Linode](http://feross.org/how-to-setup-your-linode/)
  讲述了一旦你拥有了可以正常运行的 VPS 后，怎样利用它开展工作。

* [CPU 平均负载](http://jvns.ca/blog/2016/02/07/cpu-load-averages/)
  说明了如何测量 CPU 负载以及可以利用它来做什么。

## 基础设施即服务（IaaS）
基础设施即服务（IaaS）与虚拟化服务器有重叠的部分，因为它们通常是用一种方式来呈现资源的。虚拟化服务器和 IaaS 之间的区别在于结算周期的颗粒度。IaaS 通常使用基于服务器使用的分钟数或者小时数这样更细的粒度进行结算，而不是按月结算的方式。

IaaS 可以和虚拟化服务器结合在一起为大流量访问实现动态倍增的功能。当访问流量较低时，就可以单独使用虚拟化服务器。这种资源组合的方式减少了在更加复杂的具备动态伸缩功能的基础设施上的成本。

最常见的 IaaS 平台有 
[Amazon Web 服务](http://aws.amazon.com/) 和 
[Rackspace 云服务](http://www.rackspace.com/cloud/).

IaaS 平台的缺点在于它的封闭性，如果你必须编写用于部署的自定义代码，动态调整以及想要全面地了解你的基础设施的话，那这将称为一个问题。 每个平台都有怪异的地方。例如，
Amazon 标准的基础存储设备 [弹性块存储](http://aws.amazon.com/ebs/) 的 I/O 吞吐量在最糟糕的情况下会与你本地存储设备相差一个数量级。你的应用程序在本地进行数据库查询时可能会工作地很好，但当你把它部署后会发现它的性能并没有充分发挥出来。
Amazon 还有 [高吞吐量的 EBS 实例](http://aws.amazon.com/about-aws/whats-new/2012/07/31/announcing-provisioned-iops-for-amazon-ebs/)，
但如果要使用的话，相应地也要支付更高的价格。 EBS 吞吐量只是众多怪异的特点之一，在你正式部署到一个 IaaS 平台之前，你需要了解它们。

### 与 IaaS 有关的资源
* [云服务器对比专用服务器](http://www.screamingatmyscreen.com/2012/12/the-cloud-vs-dedicated-servers/)。

* [Web 应用部署的 5 个常规服务器设置](https://www.digitalocean.com/community/articles/5-common-server-setups-for-your-web-application)
   是一个非常好的介绍，告诉你该如何安排托管。

* [Apache Libcloud](http://libcloud.apache.org/) 是一个 Python 库，它提供了针对许多云服务供应商的统一 API 接口。

* [Amazon Web 服务有官方文档](http://aws.amazon.com/python/) 讲解了运行 Python web 应用。

* [boto](https://github.com/boto/boto) 是一个可扩展并且通过良好测试的 Python 库，可以与 Amazon Web 服务配合工作。

* [Poseidon](https://github.com/changhiskhan/poseidon)  是一个用于管理 Digital Ocean 服务器的命令行接口。

## 服务器学习清单
1. 注册一个托管服务供应商。我推荐获取一个 
   [Linode VPS](https://www.linode.com/?r=bfeecaf55a83cd3dd224a5f2a3a001fdf95d4c3d) 
   进行初始化设置， 然后在上面部署你的 web 应用。 [Digital Ocean](https://www.digitalocean.com/) 和 
   [prgrmr](http://prgmr.com/xen/) 是其它的 VPS 候选供应商。在实现部署过程自动化后，你能在以后更换托管供应商。

1. 准备好你的第一个服务器。 它将处于就绪状态，但在等待你的指令时，会处于关机状态。

1. 转到 [操作系统](/operating-systems.html) 部分去学习如何加载 Ubuntu 14.04 LTS 作为部署 Python web 应用的基础系统。

