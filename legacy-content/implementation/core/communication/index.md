# 通讯机制

## 前言

在微服务架构中，为了彻底隔绝不同服务，采用了最坚决的方案：强制要求不同服务之间通过远程访问方式进行通讯。

在这点上，微服务和以OSGi为代表的Java模块化方案形成鲜明对比。

## 访问方式

在微服务间做远程访问，目前主要的方式是有以下三种类型：

1. REST
2. RPC
3. 定制

后面我们详细介绍前两种方式的做法和可选的常见实现方案。

第三中定制方式，简单说就是自己按照需要选择不同的类库：

1. 网络通讯，可以选择 netty/mina等
2. 协议可以选择 HTTP/HTTP2/TCP/UDP 等
3. 编解码方案 可以选择 Rest/protocol buffer/thrift 等

然后以上三种情况可以有多种排列组合，最后的结果可以是五花八门，就不一一列举了。

## 网络通讯类库

在涉及网络通讯时，必然会有选择网络通讯类库的问题，目前主要是各种 NIO 类库。

在介绍具体的访问方式之前，先过一下 NIO 类库，后面的各种访问方式都有可能使用到这些 NIO 类库。

## 交互方式

进程间通讯的交互方式，可以分为两个维度：

1. 第一个维度是交互对象的数量

	- 一对一： 每个客户端请求确切地被一个服务实例处理
	- 一对多： 每个客户端请求被多个服务实例处理

2. 第二个维度是交互时应答的返回方式

	- 同步： 客户端期待服务在一定时间内应答，当等待时客户端甚至会阻塞
	- 异步： 客户端在等待应答时不阻塞，而应答不需要立即发送

两个维度组合之后得到多种可能的方式：

|  | One-to-One |One-to-Many |
|--------|--------|--------|
|Synchronous| Request/response |    |
|Asynchronous|    Notification    |    Publish/subscribe    |
|Asynchronous|   Request/async response     |    Publish/async responses    |

一对一的交互方式：

- Request/response： 标准的请求/应答方式。客户端发送请求到服务并等待应答。客户端期待应答在适当的时间内到达。在基于线程的程序中，发起请求的线程在等待时可能阻塞。
- Notification(或者单路请求)： 客户端发送请求到服务但是不期待有答复。
- Request/async response： 客户端发送请求到服务，服务器端异步给回复。客户端在等待时不阻塞，而在设计上通常是假定可能不会很快就有应答。

一对多的交互方式：

- Publish/subscribe： 客户端发布通知消息，然后被0个或者多个关注的服务消费
- Publish/async responses： 客户端发布请求消息，然后等待一定数量的从关注的服务返回的应答

## 参考文档

- [Building Microservices: Inter-Process Communication in a Microservices Architecture ](https://www.nginx.com/blog/building-microservices-inter-process-communication/?utm_source=service-discovery-in-a-microservices-architecture&utm_medium=blog)




