title: 推导式
category: page
slug: comprehensions
sortorder: 0309
toc: False
sidebartitle: 推导式
meta: Python 推导式能简洁地构建列表、字典和集合。在 Full Stack Python 上了解更多信息。
authors: haiiiiiyun.github.io
updated: 2016-06-09 08:30


# 推导式
推导式是 Python 语言的构件之一，使用它能简洁地构建列表、字典和集合。列表推导式在 Python 2 中引入，而字典和集合的推导式是在 Python 3 时引用的。


## 推导式为什么很重要？
在 Python 核心数据结构中填充条件式数据，推导式是一种较清晰的语法。如果没有推导式，实现相同的功能通常需要使用嵌套的循环和条件语句，这使得代码阅读者很难进行适当的评估。

## 示例代码
列表推导式:

    >>> double_digit_evens = [e*2 for e in range(5, 50)]
    >>> double_digit_evens
    [10, 12, 14, 16, 18, 20, 22, 24, 26, 28, 30, 32, 34, 36, 38, 40, 42, 44, 46, 48, 50, 52, 54, 56, 58, 60, 62, 64, 66, 68, 70, 72, 74, 76, 78, 80, 82, 84, 86, 88, 90, 92, 94, 96, 98]


集合推导式:

    >>> double_digit_odds = {e*2+1 for e in range(5, 50)}
    {11, 13, 15, 17, 19, 21, 23, 25, 27, 29, 31, 33, 35, 37, 39, 41, 43, 45, 47, 49, 51, 53, 55, 57, 59, 61, 63, 65, 67, 69, 71, 73, 75, 77, 79, 81, 83, 85, 87, 89, 91, 93, 95, 97, 99}

字典推导式:
    
    >>> {e: e*10 for e in range(1, 11)}
    {1: 10, 2: 20, 3: 30, 4: 40, 5: 50, 6: 60, 7: 70, 8: 80, 9: 90, 10: 100}


## 推导式相关资源
* Intermediate Python 上的 [Python 推导式](http://intermediatepythonista.com/python-comprehensions) 这篇文章对 Python 这三个核心数据结构的推导式做了相当不错的总结。

* [Python 列表推导式： 可视化讲解](http://treyhunner.com/2015/12/python-list-comprehensions-now-in-color/) 讲解了这种迭代的惯用法是如何变成语言本身的语法糖的以及如何在自己的程序中使用它。

* Python 3 模式及惯用法网站对 [推导式](http://python-3-patterns-idioms-test.readthedocs.org/en/latest/Comprehensions.html) 做了总结，并用代码示例和图表讲解了它们是如何运作的。

* [以绝地武士的方式讲解 Python 的推导式](https://gist.github.com/bearfrieze/a746c6f12d8bada03589) 以星球大战的主题风格展示推导式，并演示了它的各要点知识。所有示例都用 Python 3.5 写成。

* [Python 惯用法： 推导式](https://blogs.msdn.microsoft.com/pythonengineering/2016/03/14/idiomatic-python-comprehensions/) 讲解了 Python 推导式如何受到 Haskell 列表推导式的启发。并以清晰的例子讲解推导式是如何简化普通迭代代码的--例如将一个列表复制到另一个列表并对其中的元素进行一些操作。

* [通过例子学 Python ：列表推导式](http://blog.cdleary.com/2010/04/learning-python-by-example-list-comprehensions/) 先给出一个不正确的列表推导式的例子，然后讲解如何修正错误。

* [Python 的列表推导式](http://www.pythonforbeginners.com/basics/list-comprehensions-in-python) 这篇文章涉及列表推导式代码是怎样的，并提供一些示例代码以展示它们是如何工作的。

* [Python 列表简介](http://effbot.org/zone/python-list.htm) 对 Python 列表做了大体而可靠的综述，其中当然也涉及到列表推导式。
