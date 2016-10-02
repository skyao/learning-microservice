# Spring Cloud

## 介绍

- http://projects.spring.io/spring-cloud/

Spring Cloud是一个基于Spring Boot实现的云应用开发工具，它为基于JVM的云应用开发中的配置管理、服务发现、断路器、智能路由、微代理、控制总线、全局锁、决策竞选、分布式会话和集群状态管理等操作提供了一种简单的开发方式。

## 分析

### 目标定位

前面谈到 Spring Boot的特点比较适合用来做微服务的基础框架,但是要开发一个完整的微服务系统远没有这么简单. 因此 Pivotal 为此推出了 Spring Cloud.

Spring Cloud 完全基于 Spring Boot， 是一个非常新的项目，2016年才 1.0 release。版本提升非常迅速，发展势头良好，看 Pivotal 的意义应该是冲着占领企业微服务架构这个领域去的。

### 子项目

Spring Cloud包含了多个子项目（针对分布式系统中涉及的多个不同开源产品，有近20个之多），比如：

- Spring Cloud Config

	中心化的外部配置管理，由 git 仓库支持。配置资源直接映射到 Spring `Environment` 但是如果有需要也可以被非Spring应用使用。

    > 注：这个是用来解决微服务环境下配置文件分散管理的难题，但是奇怪的是为什么要基于 git 仓库？

- Spring Cloud Netflix

	和多个 Netflix OSS 组件集成(Eureka, Hystrix, Zuul, Archaius, etc.).

    这个算是最有价值的部分，下一节单独详细介绍。

- Spring Cloud Bus

	用于将服务和服务实例连接到分布式消息的 event bus。用于在集群内传播状态变更。(如配置变更事件)

- Spring Cloud CloudFoundry

	集成应用到Pivotal Cloudfoundry。提供服务发现实现，并可以简化实现 SSO 和 OAuth2 保护的资源，也可以创建 Cloudfoundry 服务中介。

- Spring Cloud Cloud Foundry Service Broker

	提供构建服务中介的起点，管理 Cloud Foundry 管理的服务.

- Spring Cloud Cluster

	leader 选举和通用有状态模式，有抽象和用于 Zookeeper, Redis, Hazelcast, Consul 的实现。

- Spring Cloud Consul

	使用 Hashicorp 公司的 Consul 来进行服务发现和配置管理。

- Spring Cloud Security

	为负载均衡的 OAuth2 rest 客户端和在 Zuul 代理中认证 header 转发提供支持。

- Spring Cloud Sleuth

	用于 Spring Cloud 应用的分布式追踪，兼容 Zipkin， HTrace 和基于log(如 ELK)的追踪。

- Spring Cloud Stream

	消息中间件抽象层, 目前支持Redis, Rabbit MQ和Kafka

- Spring Cloud Zookeeper

	使用 Apache Zookeeper 做服务发现和配置管理。

## 总结

1. 很年轻的项目，可以关注，前景看好
2. 但是很少见到国内业界有人在生产上成套使用，一般都是只有其中一两个组件

## 参考资料

- [SpringCloud分布式开发五大神兽](https://segmentfault.com/a/1190000005029218)
