挑选解释器
======================

.. _which-python:

Python的现状（2 vs 3）
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

当选择python解释器的时候，一个首先要面对的问题是：“我应该选择Python 2还是Python 3？” 答案并不像人们想象的那么明显。

现状的基本要点如下：

1. Python 2.7 作为标准已经*很长*时间了。
2. Python 3 将重大变换引入到语言中，其中有不少开发者不满意。
3. 几年内Python 2.7 将得到必要的安全更新。
4. Python 3正在不断发展，就像Python 2在过去几年一样。

所以，你现在可以看到为什么这不是一个简单的决定了。


建议
~~~~~~~~~~~~~~~

那我直言不讳：

**用Python 3，如果：**

- 你不在乎。
- 你爱Python 3。
- 你不漠不关心2 vs 3。
- 你不知道用哪一个。
- 你接受变化。

**用Python 2，如果：**

- 你爱Python 2，对未来的Python 3感到悲伤。
- 你的软件的稳定性对语言有要求，运行时永远不会改变。
- 你依赖的软件需要它。


所以…. 3?
~~~~~~~~~

如果你选择了一种Python的解释器来用，你不是固执己见的人，我推荐你用最新的Python 3.x，因为每个版本都带来了新的改进的标准库模块，安全性和bug修复。

鉴于这样，如果你有一个强有力的理由只用Python 2，比如Python 3 无法足够替代的Python 2特有库，或者你（像我）非常喜欢，受Python 2启发。

查看`Can I Use Python 3? <https://caniusepython3.com/>`_ 来看看是否有你依赖的软件阻止你用Python 3。

`延伸阅读 <http://wiki.python.org/moin/Python2orPython3>`_

写`同时能够兼容Python 2.6，2.7，和3.3上工作的代码<http://lucumr.pocoo.org/2013/5/21/porting-to-python-3-redux/>`_ 是可能的
。这包括从简单到困难的各种难度，这取决于你写的软件的类型；如果你是初学者，其实有更重要的东西要操心。

实现方式
~~~~~~~~~~~~~~~

当人们谈论起*Python*，他们往往意味着的不仅是语言本身，还包括其CPython实现。*Python*实际上是一个语言规范，可以用许多不同的方式来实现语言。

CPython
-------

`CPython <http://www.python.org>`_ 是Python的参考实现，用C编写的。它把Python代码编译成中间态的字节码，然后由虚拟机解释。CPython为Python包和C扩展模块提供了最大限度的兼容。

如果你正在写开源的Python代码，并希望有尽可能广泛的用户，用CPython是最好的。用依赖于C扩展的包，CPython是你唯一的选择。

所有版本的Python语言都用C实现，因为CPython是参考实现。

PyPy
----

`PyPy <http://pypy.org/>`_ 是用RPython实现的解释器，RPython是Python的子集，具有静态类型这个解释器的特点是即时编译，支持多重后端（C, CLI, JVM）。

PyPy旨在最大兼容性（参考CPython的实现），同时提高性能。

如果你正在寻找提高你的Python代码的性能方法，值得试一试PyPy。在一套的基准测试下，它`比CPython的速度目前超过5倍 <http://speed.pypy.org/>`_ 。

PyPy支持Python 2.7。PyPy3 [#pypy_ver]_，发布的测试版，支持Python 3。

Jython
------

`Jython <http://www.jython.org/>`_ 是一个将Python代码编译成Java字节码的实现，运行在JVM(Java Virtual Machine)上。另外，它可以导入并用任何Java类就像Python模块一样。

如果你需要与现有的Java代码库对接或者其他原因需要为JVM编写Python代码，那Jython是最好的选择。

Jython现在支持到Python 2.5。[#jython_ver]_

IronPython
----------

`IronPython <http://ironpython.net/>`_  是一个针对 .NET framework的Python实现。它可以用Python和.NET framework的库，而且可以用.NET framework暴露Python代码给.NET框架中的其他语言。

`Python Tools for Visual Studio <http://ironpython.net/tools/>`_ 直接集成IronPython到Visual Studio开发环境中，使之成为Windows开发者的理想选择。

IronPython支持Python 2.7。 [#iron_ver]_

PythonNet
---------

`Python for .NET <http://pythonnet.github.io/>`_ 是一个包，它提供给本机已安装的Python一个.NET公共语言运行时（CLR），接近无缝集成。这所采取是与IronPython（见上文）中相反的方式，比相互竞争要更互补些。

与Mono相结合，PythonNet能使非windows操作系统的原生的Python在.NET框架中操作，比如OS X和Linux。它可以在除外IronPython的环境中无冲突运行。

PythonNet支持Python 2.3到2.7。[[#pythonnet_ver]_

.. [#pypy_ver] http://pypy.org/compat.html

.. [#jython_ver] http://wiki.python.org/jython/JythonFaq/GeneralInfo#Is_Jython_the_same_language_as_Python.3F

.. [#iron_ver] http://ironpython.codeplex.com/releases/view/81726

.. [#pythonnet_ver] http://pythonnet.github.io/readme.html
