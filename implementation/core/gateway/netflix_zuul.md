# Netflix Zuul

## 介绍

Zuul 是在云平台上提供动态路由，监控，弹性，安全等边缘服务的框架。Zuul 相当于是设备和 Netflix 流应用的 Web 网站后端所有请求的前门。Zuul 可以适当的对多个 Amazon Auto Scaling Groups 进行路由请求。

## 分析

### 定位

Zuul 在 Netflix 的微服务体系中的定位：

1. Zuul只做跨横切面的功能: 如路由，安全认证，容错，限流，日志等
2. Zuul只是一个HTTP网关: 聚合或者协议转换(如rpc转换成http)，在Edge Service层做

![](images/zuul_position.png)


## 参考资料

- [Netflix学习笔记：Zuul](http://lxlong.iteye.com/blog/2267985)
