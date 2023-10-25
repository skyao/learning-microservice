# Netflix Ribbon

## 介绍

- https://github.com/Netflix/ribbon

> Ribbon is a Inter Process Communication (remote procedure calls) library with built in software load balancers. The primary usage model involves REST calls with various serialization scheme support
>
> Ribbon 是一个进程间通讯 (RPC/remote procedure calls) 类库，内建软件负载均衡器。主要使用模式是围绕 Rest 调用，用各种序列化模式。

Ribbon 是客户端进程间通讯类库，在云中经受过考验。它提供下列特性：

- 负载均衡
- 容错
- 以异步和反应式模型执行多协议 (HTTP, TCP, UDP)
- 缓存和批量

## 分析

Ribbon 提供客户端负载均衡的支持，通常配合 Eureka 一起使用。

![](images/ribbon.png)

Ribbon客户端组件提供一系列完善的配置选项，比如连接超时、重试、重试算法等。Ribbon内置可插拔、可定制的负载均衡组件。下面是用到的一些负载均衡策略：

- 简单轮询负载均衡
- 加权响应时间负载均衡
- 区域感知轮询负载均衡
- 随机负载均衡

Ribbon中还包括以下功能：

- 易于与服务发现组件（比如Netflix的Eureka）集成
- 使用Archaius完成运行时配置
- 使用JMX暴露运维指标，使用Servo发布
- 多种可插拔的序列化选择
- 异步和批处理操作（即将推出）
- 自动SLA框架（即将推出）
- 系统管理/指标控制台（即将推出）


