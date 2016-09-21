# Mantl

## 介绍

![](images/mantl-logo.svg)

- https://mantl.io/
- https://github.com/CiscoCloud/mantl

Mantl 是 Cisco 开源的微服务平台，为用户提供了部署微服务平台所需的所有基础设施组件。

> 注： Mantl之前的名字是 "microservices-infrastructure" / "微服务-基础设置", 名字很直白但是稍微长了一点, 可能因为这个原因(我瞎猜的)所以后来更名为 mantl.


## 分析

### 定位

Mantl 对自己定义的描述：

> The bedrock of microservices infrastructure
>
> 微服务基础设施的基岩

Mantl 为微服务基础设施提供端到端的解决方案。目标是让用户专注于应用程序的代码与业务的敏捷性，而不是如何设计基础设施API。

### 功能

以下功能介绍来自 Mantl 的高层 (Cisco Intercloud Services 的 CTO Ken Owens)访谈：

- Mantl为用户提供了部署微服务平台所需的所有基础设施组件。所选择的组件都是符合业界标准的，例如Docker、Mesos 和 Terraform，并且让他们能够良好地配合运行，使用户免于编写用于整合这些组件的代码。

- Mantl能够自动完成各种任务。 这些任务在一般情况下往往需要投入几个月的时间进行DevOps。通过这种自动化能力，用户就能够专注于应用的开发，而无需在基础设施上投入过多精力。Mantl的目标是让用户专注于应用程序的代码与业务的敏捷性，而不是如何设计基础设施API。

- Mantl框架能够搭建出基础设施即服务以及软件即服务平台，使用户能够通过一种可编程的、可重复的方式部署他们的服务与应用。Mantl不限于所对应的云环境，它支持在多个云提供商的平台上进行部署，包括Rackspace、AWS、DigitalOcean和Google Cloud Platform等等。另外，用户也可以选择部署至私有云平台，包括OpenStack、VMWare、裸机，或者运行CentOS的任何系统。

### 评价

以下只是一家之言，仅供参考：

> 曾经推荐过 mantl，不过被诸多朋友诟病, 大家都认为Cisco/思科这种"大公司病"比较严重的企业, 推出的东东一定会很"重", 不适合.去 mantl 网站逛了一下, 的确是有一种"厚重"的感觉......

## 参考资料

- [通过Cisco发布的Mantl 1.0创建微服务基础设施](http://www.infoq.com/cn/news/2016/03/cisco-mantl-microservices)
- [变革中的Cisco：Matntl、Contiv、Shipped和Cisco Cloud](http://www.dockone.io/article/1103)