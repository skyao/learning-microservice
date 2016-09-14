# SpringBoot

## 介绍

Spring Boot是由 Pivotal 团队提供的全新框架，其设计目的是用来简化新Spring应用的初始搭建以及开发过程。该框架使用了特定的方式来进行配置，从而使开发人员不再需要定义样板化的配置。通过这种方式，Boot致力于在蓬勃发展的快速应用开发领域（rapid application development）成为领导者。

Spring Boot的目标不在于为已解决的问题域提供新的解决方案，而是为平台带来另一种开发体验，从而简化对这些已有技术的使用。对于已经熟悉Spring生态系统的开发人员来说，Boot是一个很理想的选择，不过对于采用Spring技术的新人来说，Boot提供一种更简洁的方式来使用这些技术。


- http://projects.spring.io/spring-boot/


## 分析

### 目标定位

Spring 框架是非常著名的 Java 开源框架，历经十多年的发展，整个生态系统已经非常完善甚至是繁杂，Spring Boot 正是为了解决这个问题而开发的，为 Spring 平台和第三方库提供了开箱即用的设置，只需要很少的配置就可以开始一个 Spring 项目。

Spring Boot 的定位：

![](images/springboot_position.png)

### 功能

Spring Boot 的主要功能：

- 创建独立 Spring 应用
- 直接内嵌 Tomcat， Jetty 或者 Undertow (不需要部署 WAR 文件)
- 提供 'starter' POM 文件来简化 maven 配置
- 尽可能的自动配置 Spring
- 提供产品级别的功能如 metrics， 健康检查和外部化配置
- 完全没有代码生成并不需要 XML 配置

## 总结

1. Spring Boot 是一个"微框架"

	离微服务框架还是有很大距离,比如没有提供最基本的服务注册和服务发现。

    当然 Pivotal 团队为此推出了解决方案 Spring Cloud。

2. Spring Boot 更适合作为一个微服务框架的**基石**

	推荐在 Spring Boot 的基础上，而不是 Spring 的基础上搭建自己的微服务框架。

3. Spring Boot 特别适合已经熟悉 Spring 体系的开发团队
