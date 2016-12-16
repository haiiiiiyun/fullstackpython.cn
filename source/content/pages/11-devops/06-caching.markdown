title: 缓存
category: page
slug: caching
sortorder: 0718
toc: False
sidebartitle: 缓存
meta: 缓存通过预先计算的常用操作结果来降低服务器负载。快来 Full Stack Python 学习更多关于缓存的知识吧。
translators: blog.chriscabin.com
updated: 2016-07-27 11:30

# 缓存
缓存通过存储预先计算常用操的作结果并将预计算的答案发送给客户端的方式来降低服务器负载。

例如，相对于从数据库表中获取不怎么变化的数据，你可以将那些值存在在内存中。从内存中获取值要远比从数据库（它将数据存储在永久存储器中，例如一块硬盘）中获取它们快得多。当缓存的值发生变化后，系统就会让缓存失效，并重新获取更新后的值以便后期请求。

堆栈中多个层都可以创建缓存。


## 缓存后端
* [memcached](http://memcached.org/) 是一种常见的内存缓存系统。

* [Redis](http://redis.io/) 是一种基于键值的内存数据存储区，它可以轻易地与诸如 [django-redis-cache](https://github.com/sebleier/django-redis-cache) 之类的库一起配置用于缓存。

## 缓存相关资源
* "[缓存：Varnish 或者 Nginx？](https://bjornjohansen.no/caching-varnish-or-nginx)"
  回顾了当选择反向代理 Niginx 或者 Varnish 时，需要考虑的一些诸如 SSL 和 SPDY 支持的问题。

* [缓存难懂，给我画幅图片](http://bizcoder.com/caching-is-hard-draw-me-a-picture)
  有一些图说明了 web 请求缓存层是如何工作的。这篇文章还是值得一读的，尽管作者在描述他的微软代码是他写作的动力。

* 虽然缓存在很多情况下都是非常有用的，但非常值得关注的是，
  [缓存也是有缺点的](https://msol.io/blog/tech/2015/09/05/youre-probably-wrong-about-caching/)，所以很多开发者才没有考虑使用它。


## 缓存学习清单
1. 分析你的 web 应用中运行最缓慢的部分。可能情况是，有些复杂的数据库查询可以预先计算并存储在内存中。

1. 确保让你的内存数据存储区已经用于会话数据，从而缓存那些复杂数据库查询的结果。一个 [任务队列](/task-queues.html) 通常可以用于定期计算结果，并将它们存放到数据存储区。

1. 采用一种缓存失效机制，从而使得给用户发送的预先计算的结果保持准确。
