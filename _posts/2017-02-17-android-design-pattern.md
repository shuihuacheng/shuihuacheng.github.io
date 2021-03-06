---
layout: post
keywords: blog
description: blog
title: "Android设计模式系列"
categories: [android_design_pattern]
tags: [android_design_pattern]
---
{% include codepiano/setup %}

# Android设计模式系列

## 简述
设计模式（Design pattern）是一套被反复使用、多数人知晓的、经过分类编目的、代码设计经验的总结。使用设计模式是为了可重用代码、让代码更容易被他人理解、保证代码可靠性。 毫无疑问，设计模式于己于他人于系统都是多赢的，设计模式使代码编制真正工程化，设计模式是软件工程的基石，如同大厦的一块块砖石一样。项目中合理的运用设计模式可以完美的解决很多问题，每种模式在现在中都有相应的原理来与之对应，每一个模式描述了一个在我们周围不断重复发生的问题，以及该问题的核心解决方案，这也是它能被广泛应用的原因。

设计模式主要基于以下的面向对象设计原则:
- **对接口编程而不是对实现编程**。
- **优先使用对象组合而不是继承**。

## 设计模式的分类
总体来说设计模式分为三大类：<br>

* 创建型模式，共5种：工厂方法模式、抽象工厂模式、单例模式、建造者模式、原型模式。
* 结构型模式，共7种：适配器模式、装饰器模式、代理模式、外观模式、桥接模式、组合模式、享元模式。
* 行为型模式，共11种：策略模式、模板方法模式、观察者模式、迭代子模式、责任链模式、命令模式、备忘录模式、状态模式、访问者模式、中介者模式、解释器模式。

**创建型模式(共5种)**
* 工厂方法模式(Factory Pattern)
* 抽象工厂模式(Abstract Factory Pattern)
* 单例模式(Singleton Pattern)
* 建造者模式(Builder Pattern)
* 原型模式(Prototype Pattern)

**结构型模式(共7种)**
* 适配器模式(Adapter Pattern)
* 装饰器模式(Decorator Pattern)
* 代理模式(Proxy Pattern)
* 外观模式(Facade Pattern)
* 桥接模式(Bridge Pattern)
* 组合模式(Composite Pattern)
* 享元模式(Flyweight Pattern)

**行为型模式(共11种)**
* 策略模式(Strategy Pattern)
* 模板方法模式(Template Pattern)
* 观察者模式(Observer Pattern)
* 迭代器模式(Iterator Pattern)
* 责任链模式(Chain of Responsibility Pattern)
* 命令模式(Command Pattern)
* 备忘录模式(Memento Pattern)
* 状态模式(State Pattern)
* 访问者模式(Visitor Pattern)
* 中介者模式(Mediator Pattern)
* 解释器模式(Interpreter Pattern)

其实还有两类：并发型模式和线程池模式。

**J2EE模式** 
* MVC模式（MVC Pattern）
* 业务代表模式（Business Delegate Pattern）
* 组合实体模式（Composite Entity Pattern）
* 数据访问对象模式（Data Access Object Pattern）
* 前端控制器模式（Front Controller Pattern）
* 拦截过滤器模式（Intercepting Filter Pattern）
* 服务定位器模式（Service Locator Pattern）
* 传输对象模式（Transfer Object Pattern）
  

## 设计模式的６大原则
#### 1、开闭原则（Open Close Principle）
**开闭原则**就是说对扩展开放，对修改关闭**。在程序需要进行拓展的时候，不能去修改原有的代码，实现一个热插拔的效果。所以一句话概括就是：为了使程序的扩展性好，易于维护和升级。想要达到这样的效果，我们需要使用接口和抽象类，后面的具体设计中我们会提到这点。

#### 2、里氏代换原则（Liskov Substitution Principle）
**里氏代换原则(Liskov Substitution Principle LSP)**面向对象设计的基本原则之一。 里氏代换原则中说，任何基类可以出现的地方，子类一定可以出现。 LSP是继承复用的基石，只有当衍生类可以替换掉基类，软件单位的功能不受到影响时，基类才能真正被复用，而衍生类也能够在基类的基础上增加新的行为。里氏代换原则是对“开-闭”原则的补充。实现“开-闭”原则的关键步骤就是抽象化。而基类与子类的继承关系就是抽象化的具体实现，所以里氏代换原则是对实现抽象化的具体步骤的规范。—— From Baidu 百科

#### 3、依赖倒转原则（Dependence Inversion Principle）
这个是开闭原则的基础，具体内容：针对接口编程，依赖于抽象而不依赖于具体。

#### 4、接口隔离原则（Interface Segregation Principle）
这个原则的意思是：使用多个隔离的接口，比使用单个接口要好。还是一个降低类之间的耦合度的意思，从这儿我们看出，其实设计模式就是一个软件的设计思想，从大型软件架构出发，为了升级和维护方便。所以上文中多次出现：降低依赖，降低耦合。

#### 5、迪米特法则（最少知道原则）（Demeter Principle）
为什么叫最少知道原则，就是说：一个实体应当尽量少的与其他实体之间发生相互作用，使得系统功能模块相对独立。

#### 6、合成复用原则（Composite Reuse Principle）
   原则是尽量使用合成/聚合的方式，而不是使用继承。


## 参考资料
[Java之美[从菜鸟到高手演变]之设计模式](http://blog.csdn.net/zhangerqing/article/details/8194653)<br>
[Android设计模式系列](http://www.cnblogs.com/qianxudetianxia/category/312863.html)<br>
[设计模式 | 菜鸟教程](http://www.runoob.com/design-pattern/design-pattern-tutorial.html)<br>
[Android源码设计模式分析项目](https://github.com/simple-android-framework/android_design_patterns_analysis)
