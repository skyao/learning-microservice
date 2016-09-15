# Netflix OSS

## 介绍

- https://netflix.github.io/

Netflix OSS 指的是 "Netflix Open Source Software"

这里我们关注的是 OSS 中的 `cloud platform`， 也就是 "Common Runtime Services & Libraries"，包括为微服务提供支持的运行时容器，类库和服务。

Netflix OSS 是一组开源的框架和组件库，是Netflix公司开发出来解决分布式系统的一些有趣的可扩展类库。对于Java开发者来说，它们是在云端环境中开发微服务的非常棒的工具代名词。在服务发现，负载均衡，容错等模式方面，都给出了非常重要的概念，并带来了漂亮的解决方案。

## 分析

### 组件和功能

主要组件包括：

- [Eureka](https://github.com/Netflix/eureka)： 服务注册和服务发现
- [Archaius](https://github.com/Netflix/archaius)： 分布式配置管理
- [Ribbon](https://github.com/Netflix/ribbon)：弹性而智能的进程间和服务通讯机制，客户端负载均衡
- [Hystrix](https://github.com/Netflix/hystrix)： 熔断器，在运行时提供延迟和容错的隔离
- [Karyon](https://github.com/Netflix/karyon)：
- [Governator](https://github.com/Netflix/governator)
- [Prana](https://github.com/Netflix/prana)
- [Zuul](https://github.com/Netflix/zuul): 服务网关
- [Fenzo](https://github.com/Netflix/Fenzo)

### 总结

Netflix OSS 是一套非常好的组件，很多情况下我们可以考虑先看看 Netflix OSS 是否有提供现成的方案，再看是否有必要自己动手造轮子。

但是，Netflix OSS 也有自生的一些不足，典型原因就是 Netflix OSS 问世比较早，在多数Netflix的开源项目开发的时期，只有AWS公有云可以选择而没有其他的替代。这个因素导致这些库并不是直接为今天采用的运行环境（如Linux上的容器）开发的。

如果开始构建微服务的方法，肯定容易被 Netflix OSS/Java/Spring/SpringCloud 所吸引。但是要知道你不是Netflix，也不需要直接使用 AWS EC2，使得应用程序变得很复杂。如今使用 docker 和采用 memos/kubernetes 是明智之举，它们已经具备大量的分布式系统特性。在应用层进行分层，是因为 netflix 5年前面临的问题，而不得不这样做（可以说如果那时有了kubernetes，netflix OSS栈会大不相同）。

因此，建议**谨慎选择，按需选择**，避免给应用程序带来不必要的复杂度。

## 参考资料

- [Netflix OSS, Spring Cloud 以及 Kubernetes？关于它们的种种！](http://www.useopen.net/blog/2016/netflix-oss-or-kubernetes-how-about-both.html)

