title: 生成器
category: page
slug: generators
sortorder: 0308
toc: False
sidebartitle: 生成器
meta: Python 生成器通过 yield 关键字能使函数的返回值表现为一个迭代器。
authors: haiiiiiyun.github.io
updated: 2016-06-08 09:24


# 生成器
生成器是 Python 的一个核心语言构件，它能使函数的返回值表现为一个迭代器。在进行大量迭代操作时，生成器能通过不断地分配和释放内存来提高内存的使用效率。 [PEP255](https://www.python.org/dev/peps/pep-0255/) 文档描述了生成器， 2001 年的 Python 2.2 首次对其进行了实现。

## Python 生成器资源
* Intermediate Pythonista 上的 [Python 生成器简介](http://intermediatepythonista.com/python-generators) 是一篇相当不错的文章，上面附有示例代码。

* 这篇名叫 [Python 生成器](http://rdrewd.blogspot.com/2014/02/python-generators.html) 的博文着重讲述了字典的生成。特别适合 Python 初学者阅读。

* [Python 201: 生成器简介](http://www.blog.pythonlibrary.org/2014/01/27/python-201-an-intro-to-generators/) 是另一篇短小精悍的文章，上面附有生成器示例代码。

* [迭代器 & 生成器](http://anandology.com/python-practice-book/iterators.html) 为这两种语言构件分别提供了示例代码，并进行了一些简单说明。

* [Python: 生成器 - 如何使用及其优点](https://www.youtube.com/watch?v=bD05uGo_sVI) 是一份屏幕录像，展示了如何在 Python 中使用生成器代码。

* Stack Overflow 上的 [怎样理解 Python 生成器？](http://stackoverflow.com/questions/1756096/understanding-generators-in-python) 这个问题有一个令人印象深刻的解答，它清晰地阐述了与 Python 生成器有关的代码和概念。

* [系统程序员生成器使用技巧](http://www.dabeaz.com/generators/) 提供了如何使用生成器的示例代码。这份资料最先是在一次针对系统程序员的 PyCon 研讨会上发布的。但是对于那些想理解如何正确使用生成器的 Python 开发人员来说，都值得一读。
