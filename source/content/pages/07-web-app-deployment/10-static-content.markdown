title: 静态内容
category: page
slug: static-content
sortorder: 0710
toc: False
sidebartitle: 静态内容
meta: 提供静态和媒体文件服务是 Python 开发中的一个重要的部分。快来 Full Stack Python 学习更多关于静态内容的知识吧！
translators: blog.chriscabin.com
updated: 2016-07-19 12:10

# 静态内容
网站中有些内容是不会改变的，所以应当直接通过 web 服务器或者内容分发网路（CDN）来为这些内容提供服务。例如 JavaScript，图片，CSS 文件等。

## 静态内容类型
静态内容可以是你开发过程中创建的一部分资源，例如登录页面的图片；也可以是用户生成的内容。Django 框架把这些分类为 *资源*  和 *媒体* 。

## 内容分发网络（CDN）
内容分发网络（CDN）是一个第三方的服务提供商，它会存储并为静态文件提供服务。例如，
[Amazon CloudFront](http://aws.amazon.com/cloudfront/)，[Akamai](http://www.akamai.com/) 和 [Rackspace Cloud Files](http://www.rackspace.com/cloud/public/files/) 都是 CDN 服务提供商。CDN 的目的是移除正在处理动态内容请求的 web 服务器的静态文件请求负载。例如，假如你有一台 512 MB 内存的虚拟私有服务器，并在上面运行着一个 nginx 服务器，它负责处理静态文件，同时又作为 Green Unicorn WSGI 服务器的前端，那么当访问流量很大时，nginx 服务器将会出现资源受限的情况。使用 CDN 可以让 nginx 服务器无需处理静态资源请求，那样的话，nginx 就可以全身心地负责给 Green Unicorn WSGI 服务器传递请求了。CDN 将会返回来自最接近请求者的数据中心的响应内容。

## 静态内容相关的资源
* [超级愚蠢白痴的 Djano, Pipeline 和 S3 入门指南](http://blog.iambob.me/the-super-stupid-idiots-guide-to-getting-started-with-django-pipeline-and-s3/)
  说明了如何在 S3 上托管静态内容，并在 Django 中使用那些文件。
  
* [破碎，缓存和在 Django 中进行 CDN 部署](http://tech.marksblogg.com/crushing-caching-cdn-django.html)
  说明了如何使用 django-compressor 和 CDN 来提供静态和媒体文件的动态伸缩服务。

* [使用 Django 上传和 Amazon S3](http://pritishc.com/blog/2015/09/06/uploading-with-django-and-amazon-s3/)
  讲解了每一个设置步骤来帮助你使用 Django 向 Amazon S3 上传文件。
  
* [使用 Amazon S3 来托管 Django 静态文件](http://blog.doismellburning.co.uk/2012/07/14/using-amazon-s3-to-host-your-django-static-files/)。

* [CDN 挂了，但你的脚本并不会](http://www.hanselman.com/blog/CDNsFailButYourScriptsDontHaveToFallbackFromCDNToLocalJQuery.aspx)。

* [django-storages](http://django-storages.readthedocs.org/en/latest/) 是一个 Django 库，用于管理在 CDN 服务商如 Amazon S3 和其他 CDN 中的静态和媒体文件。

* RevSys 有一篇非常好的文章，包含了例如设置缓存头、优化 JavaScript 和减小图片尺寸等
  [重要静态文件优化的方法](http://www.revsys.com/12days/front-end-performance/)。

* 12 个对 CDN 拥有丰富经验的人给出了他们的观点，参见这篇文章：
  [CDN 专家说 CDN](https://www.maxcdn.com/blog/cdn-experts-on-cdns/).


## 静态内容学习清单
1. 找一个内容分发网络，从而移除你的本地 web 服务器中静态内容的请求负载。我推荐使用带有  Amazon S3 CloudFont，因为它很容易设置，并且可以根据高带宽请求自动调整。

1. 更新你的 web 应用开发进度，从而将更新的静态文件上传到 CDN。

1. 将静态内容服务从 www 的子域名移动到一个静态（或者类似名称）的子域名上，这样浏览器将会在进行 www HTTP 请求时并行地加载静态内容。

