# REST

## 介绍

Rest方式是业界最流行的方案.

> 注： 我因为个人原因偏好 RPC 方案，因此对 REST 方式研究不多，这里只做简单介绍。

## 框架

- [Dropwizard](http://www.dropwizard.io/)
- [Jersey](https://jersey.java.net/)
- [Play Framework](https://www.playframework.com/)
- [Spring MVC](http://projects.spring.io/spring-framework/)
- [Spark Framework](): 轻量级的 Java web 框架,受 Ruby 框架 Sinatra 启发,适合快速开发

如果开发的 REST 服务是使用 REST 成熟度 最高的 HATEOAS (Hypermedia as the engine of application state)， 可以尝试 spring 为此推出的项目：

- [Spring HATEOAS](http://projects.spring.io/spring-hateoas/)

个人推荐，比较大众化的选择是：

1. 服务器端用 Spring mvc
2. 客户端用 Jersey

## 参考资料

- [使用 Spring HATEOAS 开发 REST 服务](http://www.ibm.com/developerworks/cn/java/j-lo-SpringHATEOAS/)