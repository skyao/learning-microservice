学习笔记: 微服务设计模式
====================

# 前言

发表在Java Code Geeks的一篇文章，介绍了六种微服务架构的设计模式。

- 原文: [Microservice Design Patterns](http://www.javacodegeeks.com/2015/04/microservice-design-patterns.html)
- 中文翻译: [微服务设计模式@infoQ](http://www.infoq.com/cn/news/2015/04/micro-service-architecture)

注: infoq的这个翻译做的非常的离谱, 对原文内容做了大量的改写和删除, 简直乱来. 很多重要信息都莫名其妙的在翻译的时候砍掉了, 本来这个文档篇幅也不多, 不知所谓. 建议阅读时多看看英文原文.

# 术语表

| 术语(English) | 翻译(中文) |
|--------|--------|
|monolithic| 单块/单体 |
|Aggregator| 聚合器 |
| dumb proxy | 哑代理 |
# 学习笔记

## 聚合器微服务设计模式 / Aggregator Microservice Design Pattern

最常用也最简单的设计模式:

![聚合器微服务设计模式](http://cdn1.infoqstatic.com/statics_s1_20151125-0108/resource/news/2015/04/micro-service-architecture/zh/resources/1.png)

聚合器调用多个服务实现应用程序所需的功能, 有多种形式

1. 简单的显式逻辑和业务逻辑

	例如一个简单的Web页面. 这种情况下Aggregator扮演的是一个简单的微服务消费者, 通过简单的调用一个或者多个微服务来实现所需的功能. 也可以有一些业务逻辑, 完成某个业务请求.

2. 更高层次的组合微服务

	Aggregator可以在组合多个微服务的基础上, 实现一定的业务逻辑和功能, 然后对外暴露为一个微服务供使用者调用.

    在某些地方将这种方式称之为**"API Gateway"**.

## 代理微服务设计模式 / Proxy Microservice Design Pattern

这是聚合器模式的一个变种:

- 客户端并不聚合数据，但会根据业务需求的差别调用不同的微服务

	即前面的聚合模式是先后调用a/b/c三个服务, 而代理模式下只会根据某个条件if一下然后选择a/b/c中的某一个做调用.

- 代理可以仅仅委派请求，也可以进行数据转换工作

![代理微服务设计模式](http://cdn1.infoqstatic.com/statics_s1_20151125-0108/resource/news/2015/04/micro-service-architecture/zh/resources/2.png)

代码模式还有一个变种, 即proxy将请求代理到固定的某一个服务, 称为"dumb proxy". 它很可能是一个"smart proxy", 将某个服务的返回转换为另外一种格式再返回给客户.

## 链式微服务设计模式 / Chained Microservice Design Pattern

链式模式在接收到请求后会先后调用多个服务,产生一个经过合并的响应给客户.

![链式微服务设计模式](http://cdn1.infoqstatic.com/statics_s1_20151125-0108/resource/news/2015/04/micro-service-architecture/zh/resources/3.png)

所有服务都使用同步消息传递:

- 在整个链式调用完成之前，客户端会一直阻塞
- 服务调用链不宜过长，以免客户端长时间等待

## 分支微服务设计模式 / Branch Microservice Design Pattern

分支模式是聚合器模式的扩展, 结合了链式模式.

![](http://cdn1.infoqstatic.com/statics_s1_20151203-0208/resource/news/2015/04/micro-service-architecture/zh/resources/4.png)

## 数据共享微服务设计模式 / Shared Data Microservice Design Pattern

重构现有的"单体应用"时，SQL数据库反规范化可能会导致数据重复和不一致。因此，在单体应用到微服务架构的过渡阶段，可以使用这种设计模式, 让两个微服务共享数据和缓存:

![数据共享微服务设计模式](http://cdn1.infoqstatic.com/statics_s1_20151203-0208/resource/news/2015/04/micro-service-architecture/zh/resources/5.png)

**不到万不得已不要这样使用!**

- 只有在两个服务之间存在强耦合关系时才可以
- 对于基于微服务的新建应用程序而言，这是一种**反模式**
- 这也可以是暂时的过度阶段, 最终还是要消除共享实现完全自治

## 异步消息传递微服务设计模式 / Asynchronous Messaging Microservice Design Pattern

同步请求会造成阻塞, 可以选择使用消息队列代替同步请求/响应:

![异步消息传递微服务设计模式](http://a3ab771892fd198a96736e50.javacodegeeks.netdna-cdn.com/wp-content/uploads/2015/04/microservices-async-messaging-1024x640-1024x640.png)

# 总结

常见的微服务设计模式并不复杂, 按照实际情况权衡选择.
