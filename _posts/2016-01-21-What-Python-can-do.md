---
layout: post
title:  "Python 能做什么？"
date:   2016-01-21
author: Zhang Yang
category: Language
tags: [python]
---

当你看到 Python 的时候， 心里想

>“蛇 ？！”，请从0节开始；  
>“这是测试的事”，请跳转第2节；  
>“脚本语言”，请跳转到3节；  
>“不适用于大工程”，请跳转4节；  

---
## 巨蟒剧团之飞行马戏团

巨蟒剧团（Monty Python），1969年10月5日，当这五个英国佬和一个美国佬第一次胡言乱语恬不知耻地出现在BBC电视台上时，整个英伦三岛都傻了眼。从这天开始，在之后短短的四年间， “巨蟒剧团” 及其六位成员的名字通过《飞翔的马戏团》这套空前成功的电视喜剧节目，很快成为了英国现代文化的一个标志。这个名字，在今天不仅仅指向他们合作的四季电视剧和四部故事片，也不只代言喜剧的后现代面孔，而俨然已经被推崇为后现代的文化符号，有喜剧界的披头士之称。CNN的追忆文章曾感慨“巨蟒改变了世界”。

---
## 正文

作为一部英国肥皂剧的脑残粉，荷兰数学家 Guido van Rossum 将他设计的一种程序设计语言，命名为 Python，它最初发布的时间是1991年。是的，今年 Python 已经24岁了，比 HTTP 1.0协议大5岁，且比 Java 大4岁. 它已经步入创业的最佳年龄了！

1996年  Google 的第一个成功的网络爬虫就是使用 Python 实现的。有趣的是，此时 Rossum 已经移居美国1年了，而他就职 Google 还要再等 9 年以后的2005年。

---

### Python 只适合测试？

关于Python是一种什么样的语言，这里不打算说对象、类之类的术语。我们可以先来看一看，时至今日 Python 都在哪些领域里得以应用：

**电信基础设施**(Twilio)  
**支付系统** (PayPal, Balanced Payments)  
**神经科学和心理学**   
**数值分析和工程** (numpy, numba)  
**动画**(LucasArts, Disney, Dreamworks)  
**游戏后台** (Eve Online, Second Life...)  
**Email 基础设施** (Mailman, Mailgun)  
**媒体存储和处理** (YouTube, Dropbox)  
**操作和系统管理** (Rackspace, OpenStack)  
**自然语言处理**(NLTK)  
**机器学习和计算机版本** (scikit-learn, Orange)  
**安全性和渗透性测试** ( eBay/PayPal )  
**大数据** (Disco, Hadoop support)  
**搜索系统** (ITA, Ultraseek, 还有 Google)  
**Internet基础设** (DNS) (BIND 10)  

在如此之多领域的公司里得到广泛使用的Python，难道只是用在它们的测试部门？至少根据网络上的谣言，豆瓣、Youbute、和 Dropbox 都是以 Python 为主体语言搭建起来的网站。Python 强大的能力（例如：网络处理能力，还有各种扩展包），可以使得程序员们把注意力投放在实现业务上，而不是内存管理，接口设计之类的细节上。


事实上，Python 最常见的应用情形是：

	1. 使用 Python 快速生成程序的原型（有时甚至是程序的最终界面，你会喜欢 wxPython 的），
	2. 对其中有特别要求的部分，使用更合适的语言（尤其是 C/C++）改写。

由于 Python 与 C 的天然联系，它们之间的相互调用从来都不是问题。特别是 Python 如何调用 C 在《 Programming Python》的 Chapter 22. Extending Python 部分有介绍。Python 调用 C 的动态/静态库并不是一件复杂的事情。实际上， Python 原生的正则表达式库就是用 C 语言实现的。

---
### Python 只是脚本语言？

Python 确实的可以完成脚本语言的功能（使用更简洁的方式）。Shell 工具往往从命令行运行，实现诸如文本文件的处理以及调用其他程序等任务。Python 能做的更多。

有专家称 Python 是大数据全栈式开发语言，在“云基础设施”、“DevOps”、"网络爬虫” 和 “数据处理”领域，Python 都是最流行的语言。

对于开源软件向来迟钝的微软参加2015年 PyCon 时高调宣布提高 Python 在 Windows 上的编程体验，包括 Visual Studio 支持 Python，优化 Python 的 C 扩展在 Windows 上的编译等等。脑补下未来 Python 作为 Windows 默认组件的场景。

---
### Python 之NB

和 Python 之禅（注1）里表述的一样，简单优雅已经深入Python骨髓。正是这个原因，Python 才被认为上手简单，开发快速，程序可读性超强；也正是这些特点，互联网公司更有意愿使用它，因为快速发布是它们的生存之根本。在实践中，程序员可以很直观地发现，用 Python 写的代码通常要比同样的 C/C++ 或 JAVA 程序要短得多。

Python

<img src="{{ '/img/python-pic/01python_short.png' | prepend: site.baseurl}}" alt="python_short" >

C++

<img src="{{ '/img/python-pic/02cpp_long.png' | prepend: site.baseurl}}" alt="02cpp_long.png" >

---
能做到这些，是因为Python
 
#### 变量不需要声明

这个真的很方便。变量的声明和定义一定会严重打断对代码逻辑的思考，还有对齐的麻烦。内存的管理，这简直都就是 C/C++ 编程中最常见的雷区，由于省略了声明，这也不再是问题了。

#### 缩进而不是 ‘{’  ‘}’

Python 是以缩进来管理代码结构的。这样做有他的优越性：程序员们一定有过漏写 '{' 或者 '}' 的经历。如果使用的编译器或者解释器优秀的话，漏去的'{' '}'的确可以非常容易的加上。但如果不是这样，请在复杂的代码中漫游一会吧。因为可能编译器会通知一个 '错误' 的错误信息，这个错误的位置可能会离你真正错误的地方很远（十万八千里?!）。相对于此，以缩进管理方式的 Python 来说，程序员几乎不用考虑这种问题。其次以缩进方式区分块的Python在进行复杂的嵌套中，Python代码就显得明了许多了。

Python

<img src="{{ '/img/python-pic/03python_clean.png' | prepend: site.baseurl}}" alt="03python_clean.png" >

C++

<img src="{{ '/img/python-pic/04cpp_complex.png' | prepend: site.baseurl}}" alt="04cpp_complex.png" >


相比较来看，Python的代码更能分清其层次，而对于C++这样的代码虽然能够编译成功。但是，对于其日后的维护，会造成无尽的痛苦。由此，可以看出 Python的语法简洁。同时，Python 的查错能力也非常强。在一般情况下，Python的解释器能够准确指出错误的位置和原因。


Python 的缩颈唯一没有做好的就是没有指定一定要缩进4个空格。


#### 强大的语句

这是 Python 最大的与众不同。我们可以看看下面的例子：

##### 多参数同时赋值

<img src="{{ '/img/python-pic/python_simple.png' | prepend: site.baseurl}}" alt="python_simple.png" >

##### 交换就可以交换
`a, b = b, a`

##### 神奇的字符串操作

<img src="{{ '/img/python-pic/python_simple2.png' | prepend: site.baseurl}}" alt="python_simple2.png" >

##### 一行的循环

<img src="{{ '/img/python-pic/python_simple3.png' | prepend: site.baseurl}}" alt="python_simple3.png" >

##### 不需要 if 的判断语句

<img src="{{ '/img/python-pic/python_simple4.png' | prepend: site.baseurl}}" alt="python_simple4.png" >

##### 打开并读取文件

<img src="{{ '/img/python-pic/python_simple8.png' | prepend: site.baseurl}}" alt="python_simple8.png" >

##### 生成函数

<img src="{{ '/img/python-pic/python_simple9.png' | prepend: site.baseurl}}" alt="python_simple9.png" >

##### 函数式编程（匿名函数）

<img src="{{ '/img/python-pic/python_simpleA.png' | prepend: site.baseurl}}" alt="python_simpleA.png" >

---

### Python之殇

#### 运行时错误

Python没有编译过程，‘int+string’的运行时错误，只有当代码被真正执行的时候，才会暴露出来。因为对于一个变量来说，在写代码的时候，有时候很容易就忘记这个变量到底是什么类型。

#### 允许同名函数

在 Python 里面，可以允许同名函数的出现，后一个函数会覆盖前一个函数，这有时候会导致系统中隐藏很严重的错误。

对于一个工程来说，这些都就意味着只有在客户真正开始使用的时候，问题才会被发现。要完全避免发生这样的事情，Python 代码的 UT 覆盖率就要做到变态的100%（或者接近100%），同时也要经常使用 PyLint 这样的代码静态检查工具。

#### 无法真正的多线程

Python 的 GIL（注2）导致无法真正的多线程，大家可能会说我用多进程不就完了。但如果一些计算需要涉及到多进程交互，进程之间的通讯开销也是不得不考虑的。


#### 安装软件包比较麻烦

部署 Python 服务的时候，需要在服务器上面安装一堆的包，这一点就很麻烦，虽然可以通过puppet，salt这些自动化工具可以解决部署问题，但相比较静态编译语言只用扔一个二进制文件而言，还是很麻烦的。



#### Python 更容易产生烂代码

这是因为 Python 更容易产生代码。Python 非常灵活简单，写 C 几十行代码才能搞定的功能，Python 一行代码没准就能解决。但正是由于太简单了，反而会导致很多程序员无法对代码进行深层次的思考，对整个架构进行细致的考量。程序员接收到一个新需求后， 啪啪啪（别想歪了），键盘敲完快速实现，结果就是代码越来越混乱，最终导致了整个项目代码失控。虽然这也可能是因为没好的代码复查机制，没有好的项目规范等原因，但如果一个程序员没经过良好的编码训练，用 Python 更容易写出烂的代码，因为太自由了。

---

### Python 适合大工程吗？


一般来说，反对者会提出“性能问题”， “运行时出错”， 和 “缺乏开发工具”等理由。但这些真的是问题吗？

现在除了超大型互联网公司需要静态语言来省电以外，没有听说过多少因为语言速度慢而出现的软件问题。何况现在慢的程序，以后未必就慢了。硬件一定会越来越快的，可是程序员的开发速度，可是一直很难提起来。

无论多么严格的检查都无法阻止程序员写出垃圾来。C的检查比C++弱，但是它在TIOBE上排得比C++要靠前。C语言相信程序员能够做好自己的事情所以没有做出过多的假定，C++看起来严格遵守了很多编程范式，其实过于复杂，直到今天，C++的编译器也不能明确地解决它最复杂的内存泄露问题，这个检查有等于没有。

实际上IDLE已经非常好用了，而且还有Eclipse这个神器在；不论是编辑 Python 还是 Python 的 UT 都已经支持的非常不错了。C++倒是什么工具都有，这让它变好了吗？

其实Python做大项目没什么问题，至少不会比其它主流语言更差，项目的可控规模多大，主要还是取决于人，不是语言——语言当然有差别，但是没有宣传的那么大。至于错误在运行时，这就看自动化测试的水平了。Python项目出现的bug不会比C++或Java更高。

最后说一个题外话：

	好奇号宇宙飞船的两百五十万行的代码，绝大部分都是用Python书写，然后生成C再执行的。

---

### 从现在起，从自己做起


不论之前是如何看待 Python 的，希望在看到这里的时候，你愿意动手去写简单 Python 小工具（例如：批量修改文件名、用正则表达式搜索文件、甚至Windows GUI），而不是使用那些破解版的工具（^-^），或者愿意在你正在工作的项目中尝试使用它在制作原型，那就更完美了。



注1： 了解完整的Python 哲学理念，可以在任意一个Python 交互解释器中键入import this 命令

注2：GIL，即全局解释器锁（Global Interpreter Lock）。
