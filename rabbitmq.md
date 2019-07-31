message broker
====
```
消息代理将消息发布者那接收到的消息根据既定的路由发送给消费者
```
AMQP实体
==
```
队列，交换机，绑定统称为AMPQ实体(amqp entities)
```


exchange
==
```
交换机是用来发送消息的amqp实体，它会将拿到的消息路由给一个或0个对队列，
具体的路由算法更加相应的binging确定。AMQP091代理提供了如下四种交换机类型：
1、Direct Exchange
2、Fanout Exchange
3、Topic Exchange
4、Header Exchange
```

如何保证消息送达消费
==
```
rabbitmq 通过acknowledgement(通知) 保证至少一次送达[等待client通知回复了broker才会走后续的操作]
(消费端在收到消息后通知broker)
rabbitmq通过confirm告知publisher收到消息(如果没有收到confirm，生产者应该主动重新发送，这中间可能出现多条消息，比如confirm中途网络原因失败了)
```
如何避免消息重复消费或者保证消费的幂等性
```
消息消费处理器保证幂等性处理（每个消息做有个唯一的id，统一处理）
```

==
消息时序性
==
