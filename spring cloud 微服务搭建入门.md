服务注册和发现
===
分布式环境中，服务器越来越多，服务越来越多，
于是就有了服务注册和服务发现，方便服务的管理
服务启动后可以向服务中心自动的注册服务，需要调用该服务的客户端可以通过服务中心查找到服务，这样一来无需硬编码方式去找url是什么，服务在哪里等。

服务负载均衡
==
一个服务可能有多个实例，在多个实例中，客户端如何确定调用哪个实例，这就涉及到了负载均衡

服务配置中心
==
服务很多，自然而然的配置文件就会多，如果分散在各个地方，修改起来就会变得很麻烦。于是中心化的配置中心就出来了，
由于单机版本的中心容易出现故障，集群化的配置中心自然而然的就是需要要实现的点了。

熔断
===
一台机器，错误的概率可能是千分之一，但是两台服务都不出错的概率概率就是1/1000*1/1000了，服务一多，要保证都不出错基本是不可能的。
服务划分的小了之后，一个系统调用N个服务也是常有的事情，如果避免一个服务的失败导致占用了整个服务的资源，进而整个系统垮掉呢？
这个时候就来了熔断隔离之术。

Hystrix

网关
===
服务划分变小后，对外界来说一个业务功能可能需要N个服务进行配合，如果所有的端口都要进行配置，这会赵成很大的麻烦，管理起来也不容易。这样网关就出现了，对外提供统一的入口，可进行服务的路由配置，可鉴权

监控
==
裸跑的系统即使你自己开发完了也会担心，如果进行服务的有效监控呢？


服务划分
===
都知道微服务会带来不少好处，可是服务具体怎么划分，要拆分到多小，边界时什么？

领域驱动模型
===
