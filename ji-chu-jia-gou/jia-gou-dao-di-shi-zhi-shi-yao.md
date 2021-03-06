# 架构到底是指什么

梳理几个有关系又相似的概念 :

系统与子系统 , 模块与组件 , 框架与架构 .

#### 系统与子系统

> **系统**泛指由一群有关联的个体组成 , 根据某种规则运作 , 能完成个别元件不能单独完成的工作的群体 . 它的意思是"整体"或"联盟" .

1.**关联**:系统是由一群有关联的个体组成的 , 没有关联的个体堆在一起不能成为一个系统 .

2.**规则**:系统内的个体需要按照指定的规则运作 , 而不是单个个体各自为政 . 规则规定了系统内个体分工和协作的方式 .

3.**能力**:系统能力与个体能力有本质的差别 , 系统能力不是个体能力之和 , 而是产生了新的能力 .

> **子系统**也是由一群有关联的个体所组成的系统 , 多半会是更大系统中的一部分 .

其实子系统的定义和系统的定义是一样的 , 一个系统可能是另外一个更大系统的子系统 .

以微信为例分析 :

1.微信本身是一个系统 , 包含聊天 , 登录 , 支付 , 朋友圈等子系统 .

2.朋友圈这个系统又包括动态 , 评论 , 点赞等子系统 .

3.评论这个系统可能又包括防刷子系统 , 审核子系统 , 发布子系统 , 存储子系统 .

4.评论审核子系统不再包含业务意义上的子系统 , 而是包括各个模块或组件 , 这些模块或组件本身也是另外一个维度上的系统 . 例如 , MySQL , Redis等是存储系统 , 但不是业务子系统 .

#### 模块与组件

> 软件模块\(Module\)是一套一致而互相有紧密关联的软件组织 . 它分别包含了程序和数据结构两部分 . 现代软件开发往往利用模块作为合成的单位 .
>
> 模块的接口表达了由该模块提供的功能和调用它时所需的元素 . 模块是可能分开被编写的单位 . 这使它们可再用和允许人员同时协作 , 编写及研究不同的模块 .
>
> 软件组件定义为自包含的 , 可编程的 , 可重用的 , 与语言无关的软件单元 , 软件组件可以很容易被用于组装应用程序中 .

**模块和组件都是系统的组成部分 , 只是从不同的角度拆分系统而已 . **

从逻辑的角度来拆分系统后 , 得到的单元就是模块 ;

从物理的角度来拆分系统后 , 得到的单元就是组件 ;

划分模块的主要目的是职责分离 ;

划分组件的主要目的是单元复用 ;

以网站系统为例 , 一个学生信息管理系统 :

从逻辑的角度来拆分 , 可以分为"登录注册模块" , "个人信息模块" , "个人成绩模块" ;

从物理的角度来拆分 , 可以分为"Nginx" , "Web服务器" , "MySQL" ;

#### 框架与架构

> 软件框架\(Software Framework\) 通常指的是为了实现某个业界标准或完成特定基本任务的软件组件规范 , 也指为了实现某个软件组件规范时 , 提供规范所要求之基础功能的软件产品 .

1. 框架是组件规范 :  例如 , MVC就是一种最常见的开发规范 , 类似的还有MVP , MVVM , J2EE等框架 . 
2. 框架提供基础功能的产品 : 例如 , SpringMVC是MVC的开发框架 , 除了满足MVC的规范 , Spring提供了很多基础功能来帮助我们实现功能 , 包括注解\(@Controller等\) , Spring Security , Spring JPA等很多基础功能 . 

> 软件架构指软件系统的"基础结构" , 创造这些基础结构的准则 , 以及对这些结构的描述 .

框架关注的是规范 , 架构关注的是结构 . 框架的英文是Framework , 架构的英文是Architechture .

实际工作中 , 框架和架构总是说的模棱两可 , 根本原因隐藏于框架的定义中 , 关键就是基础结构这个概念没有明确说是从什么角度来分解的 . 采用不同的角度或者维度 , 就可以将系统划分为不同的结构 .

例如 , 从业务逻辑的角度分解 , "学生管理系统"的架构是 :

![](/assets/luojijiaodu.png)

从物理部署的角度分解 , "学生管理系统"的架构是 :

![](/assets/wulibushu.png)

从开发规范的角度 , "学生管理系统"可以采用标准的MVC框架来开发 , 因此架构又变成了MVC .

![](/assets/kaifaguifan.png)

上面这些"架构" , 都是"学生管理系统"正确的架构 , 只是从不同的角度来分解而已 , 这也是IBM的RUP将软件架构视图分为著名的"4+1视图"的原因 .

> 扩展阅读
>
> [https://blog.csdn.net/apanious/article/details/51011946](https://blog.csdn.net/apanious/article/details/51011946)

#### 重新定义架构

软件架构指软件系统的顶层结构 .

首先 , 系统是一群关联个体组成的 , 这些个体可以是子系统 , 模块 , 组件等等 . 架构需要明确系统包含哪些个体 .

其次 , 系统中的个体需要"根据某种规则"运作 , 架构需要明确个体运作和协作的规则 .

第三 , 维基百科定义的架构用到了"基础结构"这个说法 , 这里改为"顶层结构" , 可以更好的区分系统和子系统 , 避免将系统架构和子系统架构混淆在一起导致架构层次混乱 . 

---

架构是顶层设计 ; 

框架是面向编程或配置的半成品 ; 

组件是从技术维度上的复用 ; 

模块是从业务维度上职责的划分 ; 

系统是相互协同可运行的实体 . 

