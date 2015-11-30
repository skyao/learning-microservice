Martin Fowler的《微服务》
=======================

# 前言

Martin Fowler的《微服务》是第一篇详细介绍微服务的文章。对微服务进行了定义，并与传统架构进行了对比，阐述了微服务的优势。

- 原文: [microservices](http://martinfowler.com/articles/microservices.html)
- 中文翻译: [微服务](http://www.jdon.com/46204)

注: 发现上面的翻译工作做的也不是特别好, 在学习的同时顺便润色了一下, 向原翻译同学致敬!

# 正文

"Microservices" - yet another new term on the crowded streets of software architecture. Although our natural inclination is to pass such things by with a contemptuous glance, this bit of terminology describes a style of software systems that we are finding more and more appealing. We've seen many projects use this style in the last few years, and results so far have been positive, so much so that for many of our colleagues this is becoming the default style for building enterprise applications. Sadly, however, there's not much information that outlines what the microservice style is and how to do it.

"微服务"，在软件架构这个拥挤的街道上冒出来的又一个新名词。虽然我们本能是轻蔑的瞥了一眼这些事情，但是这个术语描述了一个越来越吸引人的软件系统风格。在过去几年中我们看到很多项目在使用这种风格，而结果都是积极正面的，以至于对于我们许多同事微服务变成了构建企业级应用的默认风格。但遗憾的是，没有太多信息来概述什么是微服务风格和该如何做。

In short, ++**the microservice architectural style is an approach to developing a single application as a suite of small services, each running in its own process and communicating with lightweight mechanisms**++, often an HTTP resource API. These services are built around business capabilities and independently deployable by fully automated deployment machinery. There is a bare minimum of centralized management of these services, which may be written in different programming languages and use different data storage technologies.

简单说，++**微服务架构风格是一种通过一套小型服务来开发单个应用的方法，每个服务运行在自己的进程中，并通过轻量级的机制进行通讯**++，经常是基于HTTP资源API，这些服务基于业务能力构建，能够通过自动化部署方式独立部署，这些服务自己有一些小型集中化管理，可以是使用不同的编程语言编写，正如不同的数据存储技术一样。

To start explaining the microservice style it's useful to compare it to the monolithic style: a monolithic application built as a single unit. Enterprise Applications are often built in three main parts: a client-side user interface (consisting of HTML pages and javascript running in a browser on the user's machine) a database (consisting of many tables inserted into a common, and usually relational, database management system), and a server-side application. The server-side application will handle HTTP requests, execute domain logic, retrieve and update data from the database, and select and populate HTML views to be sent to the browser. This server-side application is a monolith - a single logical executable[2]. Any changes to the system involve building and deploying a new version of the server-side application.

为了开始解释微服务，必须比较一下铁板一块式monolithic(整体) 风格，一个铁板一块monolithic的应用作为一个单元构建，企业应用经常基于三个部分构建：一个客户端用户界面(浏览器运行HTML和javascript)，一个数据库和一个服务端应用，服务端应用处理Http请求，执行领域逻辑，加载和更新数据库数据，查询和导出Html视图到浏览器，这个服务端应用是铁板一块monolithic ，只有一个合乎逻辑的可执行文件，这个系统的任何改变都会涉及到重新构建和部署新版本。