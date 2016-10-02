# 服务注册/发现

## 基于分布式一致性的方案

目前服务注册/发现的解决方案，如果希望实现分布式一致性，通常的选择有：

- Eureka
- Consul
- Etcd
- Zookeeper: 来自 apache，使用最广泛
- SmartStack

![](images/implementation_list.png)

主要的一致性协议有：

- POXOS： Zookeeper
- Raft： Consul / Etcd

## 简单实现方案

也有不是很介意分布式一致性，而采用自行实现的简单方案：

- 基于redis

	如新浪的Motan："Motan 可以支持不同的注册中心，如 ZK、Consul，目前使用的注册中心是平台开发的 Vintage，Vintage 是一个基于 Redis 的轻量级 KV 存储系统，能够提供命名空间服务、服务注册、服务订阅等功能。"。

    > 注：已经和 Tim Yang 老师确认，目前的确还是如此。

## 内建服务注册的框架

服务注册是任何一个SOA/服务化/微服务框架的必不可少的一个部分，因此很多框架都内建了对服务注册的支持：

- dubbo：支持注册中心扩展，支持多个实现
- motan：提供对 Zookeeper 和 Consul 的支持
- Spring Cloud： 提供子项目如Spring Cloud Consul/Spring Cloud Zookeeper

## 参考资料

- [服务发现方案梳理及NetflixEureka简介](https://segmentfault.com/a/1190000004944218)