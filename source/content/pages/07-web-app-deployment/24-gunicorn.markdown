title: Green Unicorn (Gunicorn)
category: page
slug: green-unicorn-gunicorn
sortorder: 0724
toc: False
sidebartitle: Green Unicorn (Gunicorn)
meta: Green Unicorn (Gunicorn) 是一个 Python WSGI 服务器，它会运行 Python web 应用代码。
translators: blog.chriscabin.com
updated: 2016-08-01 15:40


# Green Unicorn (Gunicorn)
[Green Unicorn](http://gunicorn.org/)，通过常简称“Gunicorn”，它是 [Web 服务器网关接口（WSGI）服务器](/wsgi-servers.html)的一种实现，通常用于运行 Python web 应用。

<a href="http://gunicorn.org/" style="border: none;"><img src="/img/gunicorn-logo.jpg" width="100%" alt="Official Green Unicorn (Gunicorn) logo." class="technical-diagram"></a>


## Gunicorn 为何很重更要？
Gunicorn 是众多 WSGI 服务器实现之一，但它特别重要，因为它稳定，是[web 应用部署](/deployment.html) 中常用组成部分，它驱动着一些世界上最大的基于 Python 的 web 应用，例如 [Instagram](http://instagram-engineering.tumblr.com/post/13649370142/what-powers-instagram-hundreds-of-instances)。

Gunicorn 实现了 [PEP3333 WSGI 服务器标准规范](https://www.python.org/dev/peps/pep-3333/) 接口，这样它就可以运行那些实现了应用接口的 Python web 应用。例如，假设你使用了诸如 [Django](/django.html)、[Flask](/flask.html)、或 [Bottle](/bottle.html) 这样的 [web 框架](/web-frameworks.html) 编写了一个 web 应用，那么你的应用就实现了 WSGI 规范。

<div class="well see-also">Gunicorn 是<a href="/wsgi-servers.html">WSGI 服务器</a> 概念的一种实现。在<a href="/deployment.html">部署</a> 章节学习如何将这些部分组合在一起，或者查看所有主题的<a href="/table-of-contents.html">目录</a>。</div>


## Gunicorn 如何知道怎样运行我的 web 应用？
Gunicorn 根据在 WSGI 服务器和 WSGI 兼容的 web 应用之间的钩子知道如何运行 web 应用。

这儿有个例子，它说明了如何通过 Gunicorn 运行一个典型的 Django web 应用。
我们将以 [dango\_defaults](https://github.com/mattmakai/compare-python-web-frameworks/tree/master/django_defaults) 为例。在 [django\_defaults](https://github.com/makaimc/compare-python-web-frameworks/tree/master/django_defaults/django_defaults) 项目目录中，有一个短的 [wsgi.py](https://github.com/makaimc/compare-python-web-frameworks/blob/master/django_defaults/django_defaults/wsgi.py) 文件含有下面的内容：

    """
    WSGI config for django_defaults project.

    It exposes the WSGI callable as a module-level variable named ``application``.

    For more information on this file, see
    https://docs.djangoproject.com/en/1.8/howto/deployment/wsgi/
    """

    import os

    from django.core.wsgi import get_wsgi_application

    os.environ.setdefault("DJANGO_SETTINGS_MODULE", "django_defaults.settings")

    application = get_wsgi_application()

`wsgi.py` 文件是在 Django 项目首次创建时通过 `django-admin.py startproject` 命令生成的。
Django 通过 `wsgi.py` 文件暴露了一个 `application` 变量，这样 WSGI 服务器就可以使用 `application` 作为一个钩子来运行 web 应用。
下图是对这个情况的直观展示：

<img src="/img/gunicorn-django-wsgi.png" alt="Gunicorn WSGI server invoking a Django WSGI application." width="100%" class="technical-diagram" />


## 什么叫做“预分叉”工作者模型？
相对一个工作者模型结构，Gunicorn 是基于预分叉工作模型的。预分叉工作模型是指主线程使工作者自旋处理请求，却不控制这些工作者如何执行请求处理任务。每个工作者都独立于控制者。

### Gunicorn 相关资源
* 在 [Full Stack Python 博客](/blog.html) 中有三篇针对框架的文章说明了如何在 Ubuntu 上配置 Gunicorn 用于开发：
    1. [在 Ubuntu 16.04 LTS 上设置 Python 3、Django 和 Gunicorn](/blog/python-3-django-gunicorn-ubuntu-1604-xenial-xerus.html)。
    1. [如何在 Ubuntu 16.04 LTS 上设置 Python3、Flask 和 Green Unicorn](/blog/python-3-flask-green-unicorn-ubuntu-1604-xenial-xerus.html)。
    1. [在 Ubuntu 16.04 LTS 上配置 Python 3、Bottle 和 Gunicorn 用于开发](/blog/python-3-bottle-gunicorn-ubuntu-1604-xenial-xerus.html)。

* [Gunicorn 作为你的 Django 开发服务器](https://vxlabs.com/2015/12/08/gunicorn-as-your-django-development-server/)
是一个短篇，含有一些使用 Gunicorn 用于本地应用开发的优秀建议。

* [全栈 Python 部署指南](http://www.deploypython.com/)
提供了详细的指导步骤用于将 Gunicorn 作为一个完整 Python web 应用部署的一部分。

* [Flask 在 Nginx 和 Gunicorn 上](http://prakhar.me/articles/flask-on-nginx-and-gunicorn/)
在部署中将 Gunicorn 和  [Nginx web 服务器](/nginx.html) 在一起为一个 Flask 应用提供服务。

* 问题“[使用 Gunicorn 运行 Django 的最佳实践是什么？](http://stackoverflow.com/questions/16857955/running-django-with-gunicorn-best-practice)”的答案
给出了一些在部署中 Gunicorn 如何调用 Django 提供的可调用应用变量的细微差别。

* [如何在 FreeBSD 10.2 上安装 Django 和 Gunicorn 以及 Nginx](http://linoxide.com/linux-how-to/install-django-gunicorn-nginx-freebsd-10-2/)
是一个针对 FreeBSD 的教程，相对于 Ubuntu 和 CentOS 的教程，这个教程中的演示并不常见。

* [如何在 Ubuntu 14.04 上使用 Flask、Gunicorn 和 Nginx 制作一个可扩展的 Python web 应用](http://www.philchen.com/2015/08/08/how-to-make-a-scalable-python-web-app-using-flask-and-gunicorn-nginx-on-ubuntu-14-04)
和
[在 Ubuntu 上部署一个 Flask 应用](https://github.com/defshine/flaskblog/wiki/Deploy-Flask-App-on-Ubuntu(Virtualenv-Gunicorn-Nginx-Supervisor))，
这两篇文章都提供了在 Flask web 应用中设置使用 Gunicorn 的方法。
每篇教程都没有提供更多的说明，但它们在你使用 Ubuntu 遇到问题时仍然是非常好的准确参考。

* [Django](https://docs.djangoproject.com/en/1.9/howto/deployment/wsgi/gunicorn/)  和 [Flask](http://flask.pocoo.org/docs/0.10/deploying/wsgi-standalone/) 
文档中都包含了在对应框架中使用 Gunicorn 的部署指导。

* [使用 Supervisor 控制一个虚拟环境，并在该虚拟环境中设置 Django、Nginx 和 Gunicorn](https://gist.github.com/Atem18/4696071)
是一个 GitHub Gist，非常好地说明了为何需要设置 virtualenv 以及在你部署时应当注意什么。
