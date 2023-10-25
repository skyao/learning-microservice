# 消息队列

## 主流实现

### RabbitMQ

![](images/rabbitmq_logo.png)

- https://www.rabbitmq.com

### Apache Kafka

![](images/kafka_logo.png)

- http://kafka.apache.org

### Apache ActiveMQ

![](images/activemq_logo.png)

- http://activemq.apache.org

### NSQ

![](images/nsq_logo.png)

- http://nsq.io/

NSQ最初为提供短链接服务的应用 Bitly 而开发。

### 建议

对于消息系统，个人的建议：

- 轻量级 选择 RabbitMQ
- 重量级 选择 Kafka
- 如果没有历史原因，不要再选择 ActiveMQ
- 要求非常高，考虑一下 NSQ

## 参考资料

- RabbitMQ

    - [Event-driven Microservices Using RabbitMQ](http://blog.runnable.com/post/150022242931/event-driven-microservices-using-rabbitmq)
    - [使用RabbitMQ的事件驱动微服务](http://dockone.io/article/1708?utm_source=tuicool&utm_medium=referral): 上文的中文翻译


- NSQ

    - [NSQ：分布式的实时消息平台](http://www.infoq.com/cn/news/2015/02/nsq-distributed-message-platform/)
    - [Scaling NSQ to 750 Billion Messages](https://segment.com/blog/scaling-nsq/)
    - [[译]我们是如何使用NSQ处理7500亿消息的](http://www.tuicool.com/articles/EraiIvj): 上文的中文翻译

