---
layout: post
title:  "《重构》 读书笔记"
date:   2016-01-21
author: Zhang Yang
category: cleancode
tags: [coding]
---

## 第一章

### 为什么重构？
长代码本身并不带来伤害，但它往往意味着

1. 增加被修改的难度;
2. 如果简单的修改会带来重复代码，还会加剧恶化
3. 很难完成客户的需求

### 如何重构：

* 重构的第一步：建立可靠的测试环境，不一定就是UT，但是一定要能够经常运行，而且self-checking
* 按分块，封装函数
* 消除临时变量
* 按照最接近原则搬移函数，减少跨模块的依赖
* 每次都是小改动，每次修改都必须比较小，这样容易发现问题出在哪里

#### 封装函数 
降低代码重复量，是一个好的开始：

1. 封装循环体，封装代码块
2. 新函数内部，定义（或修改）局部变量，虚参取更有意义的名称，返回值取名‘result’，
3. 观察新的函数，与哪个类关系更紧密，再决定它应该属于哪个class   --> module
4. 每次搬移函数，之后都要注意是否需要变更函数名，和是否去掉参数
5. 最后查找是否有别的地方，可以直接调用被抽取的函数
 
#### 取消临时变量的原则
* Replace Temp with Query:当某个临时变量只会被修改一次的时候，可以取消该局部变量，但有性能上的隐患
* 消除临时变量，会带来更多的重复代码和性能风险；
* 书上的建议除非有profile否则不要担心性能

##### 分块的函数，往往已经告诉了我们如何分割大函数的刀口

#### 减弱依赖：
一个对象(模块)的行为，依据另一个对象(模块)的某个属性；是不好的；
至少要依据自己的数据；

1. 这种情况暗示，该行为很可能应该属于(定义在)另一个类(模块)；
2. 行为（函数）应该和更容易发生需求变化的数据更近些
 
##### 使用多态性替代switch语句，strategy/state pattern（合并多个switch到最少）

#### 关注变化，分层重构
* 最后产生四种类：Customer， Rental, Movie, Price(CommonPrice, ChildPrice, NewPrice);
* Rental作为Customer的代理，访问Movie，这样Movie的修改，最多只会影响到Rental


## 第二章
* 目的：更容易被理解，和被修改
* 方向：消除重复代码
* 原则：三次法则
* 用处
  * 重构 改进软件设计， 使得代码持续保持原来的形态； 消除重复代码
  * 重构 是原件更容易被理解，不需要记住代码，而是阅读代码
  * 重构 帮助找臭虫
  * 重构 帮助提高编程速度，良好的设计才能达成快速开发；减少调试的时间；避免补丁
* 时机和动机
  * 增加新功能的时候：为了我下次看到这段代码的时候更容易理解，代码的设计无法帮助我轻松添加特性
  * 修补错误的时候：代码还不够清晰到，我能一目了然的发现臭虫（为什么UT/MT没有发现bug）
  * 复审代码时重构，开发者设身处地的为不熟悉代码行为的人设想；提出建议的人，尝试自己先实现一下；UML, CRC
* 重构的难题
  * 数据库，对象模型和数据库模型之间，加入分割层，当对象模型不稳定时在产生
  * 修改接口，请尽量这么做：让旧接口调用新接口。
* 设计：
  * 你仍然做预先设计，但是不必一定找出正确的解决方案。此刻的你只需要得到一个足够合理的解决方案就够了；
  * 仍旧需要思考潜在的变化
* 关于性能：哪怕你完全了解系统，也请实际量测它的性能，
* 争议：取消临时变量，带来了什么好处？


##第三章

* 重复代码
* 长函数： 每当感觉需要以注释来说明点什么的时候，我们就把需要说明的东西写进一个独立函数中，并以其用途（而非实现手法）命名。
  * 如果函数内有大量的参数和临时变量，运用Extract Method会把许多这些参数和临时变量当做参数，传递给被提炼出来的新函数，导致可读性几乎没有任何提升
* 冗长类： 出现太多instance变量
* 长参数列： 除此之外就只能选择全局数据，而全局数据是邪恶的东西。对象技术改变了这一情况
* 发散式变化： 某个class经常因为不同的原因在不同的方向上发生变化
* 霰弹式修改：每遇到某种变化，你都必须在许多不同的classes内作出许多小修改以响应之
* 依恋情结： 函数对某个class的兴趣高过对自己所处之host class的兴趣
* 数据泥团：「总是绑在一起出现的数据」真应该放进属于它们自己的对象中
* 基本型别偏执：将原本单独存在的数据值替换为对象
* switch惊悚现身：switch语句的问题在于重复（duplication）。
  * 你常会发现同样的switch语句散布于不同地点。如果要为它添加一个新的case子句，你必须找到所有switch语句并修改它们。
* 平行继承体系：每当你为某个class增加一个subclass，必须也为另一个class相应增加一个subclass
* 冗赘类：如果一个class的所得不值其身价，它就应该消失
* 夸夸其谈未来性：
* 令人迷惑的暂时值域：
* 过度耦合的消息链：实际代码中你看到的可能是一长串getThis()或一长串临时变量
* 中间转手人：某个class接口有一半的函数都委托给其它class，这样就是过度运用
* 狎昵关系：两个classes过于亲密，花费太多时间去探究彼此的private成分
* 异曲同功的类
* 不完美的程序库类
* 纯稚的数据类：拥有一些值域（fields），以及用于访问（读写）这些值域的函数，除此之外一无长物
* 被拒绝的遗赠：subclasses应该继承superclass的函数和数据。但如果它们不想或不需要继承，
* 过多的注释
