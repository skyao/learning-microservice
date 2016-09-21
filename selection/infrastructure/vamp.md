# Vamp

## 介绍

![](images/vamp_logo.svg)

- http://vamp.io
- https://github.com/magneticio/vamp/

Vamp 是 "Very Awesome Microservices Platform" 的缩写, 翻译成中文, 就是大家耳熟能详的"一个神奇的微服务平台".

VAMP 由 Magnetic.io 打造，是一个开源微服务部署平台，该平台为开发、A/B测试、金丝雀发布（Canary releasing）、自动缩放，以及集成式度量指标和事件引擎提供了一种“平台中立的微服务DSL”。

## 分析

### 定位

VAMP本身并不是一个完整的微服务/容器类PaaS/堆栈，而只是专注于专门为通用微服务/容器堆栈提供高层次的金丝雀测试/发布和自动缩放功能。

VAMP能与很多容器和微服务平台集成，例如Mesosphere的Open DC/OS、Apache Mesos/Mesosphere Marathon、Docker Swarm以及（很快即将支持的）Kubernetes，当然还有诸如Cisco的Mantl、CapGemini的Apollo，或Rancher Labs的Rancher等堆栈，以及诸如MS Azure Container Service等容器云，这些容器的编排程序都能与VAMP进行集成。

## 参考资料

- [专访VAMP创作者Olaf Molenveld：为微服务平台探寻适合的抽象](http://www.infoq.com/cn/news/2016/07/vamp-microservices-platform)