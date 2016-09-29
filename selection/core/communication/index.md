# 通讯机制

## 前言

在微服务架构中，为了彻底隔绝不同服务，采用了最坚决的方案：强制要求不同服务之间通过远程访问方式进行通讯。

在这点上，微服务和以OSGi为代表的Java模块化方案形成鲜明对比。

## 访问方式

在微服务间做远程访问，目前主要的方式是有以下三种类型：

1. REST
2. RPC
3. 自己定制

后面我们详细介绍这三种方式的做法和可选的常见实现方案。

## 网络通讯类库

在涉及网络通讯时，必然会有选择网络通讯类库的问题，目前Java的NIO类库的选择很多，比较推荐的是下面几个。

#### Netty

- http://netty.io/

Netty是由JBOSS提供的一个java开源框架。Netty提供异步的、事件驱动的网络应用程序框架和工具，用以快速开发高性能、高可靠性的网络服务器和客户端程序。

是目前最流行的 NIO 方案，最新版本 4.1, 主要提供了对 HTTP 2.0 的支持。

特别提醒： **Netty 5.* 已经被废弃！**

- 具体的说明请见：https://github.com/netty/netty/issues/4466
- 主要理由是: 使用 ForkJoinPool 的主要改动增加了复杂度但是并没有显示出明确的性能收益。(原文：The major change of using a ForkJoinPool increases complexity and has not
demonstrated a clear performance benefit.)
- 因此目前 Netty 官方已经放弃了 netty 5.× 版本的开发和更新，并且推荐已经使用 netty 5.× alpha版本的同学退回到 4.0或者4.1版本

#### Mina

#### 