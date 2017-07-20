Redis是REmote DIctionary Server的缩写  

官方文档：  
[https://redis.io/documentation](https://redis.io/documentation)
中文翻译
[http://www.redis.cn/documentation.html](http://www.redis.cn/documentation.html)

# Programming with Redis
* [The full list of commands](https://redis.io/commands) Redisd 所有命令
* [Pipelining](https://redis.io/topics/pipelining) 管道，可以做一些批处理
* [Redis Pub/Sub](https://redis.io/topics/pubsub) Redis 的消息队列？
* [Redis Lua scripting](https://redis.io/commands/eval) 对Lua脚本语言的支持？
* [Debugging Lua scripts](https://redis.io/topics/ldb) 对Lua脚本语言的支持？
* [Memory optimization](https://redis.io/topics/memory-optimization) 内存优化，需要再仔细看看。
* [Expires](https://redis.io/commands/expire) 过期策略
* [Redis as an LRU cache](https://redis.io/topics/lru-cache) 使用的是近似LRU算法，选5个删一个。
* [Redis transactions](https://redis.io/topics/transactions) 是我，MULTI命令开始，EXEC 提交。
* [Mass insertion of data](https://redis.io/topics/mass-insert) 客户端批量插入
* [Partitioning](https://redis.io/topics/partitioning 分区 RedisCluster、Proxy、客户端一致性hash
* [Distributed locks](https://redis.io/topics/distlock) 分布式锁
* [Redis keyspace notifications](https://redis.io/topics/notifications)
* [Creating secondary indexes with Redis](https://redis.io/topics/indexes) Redis 里也有索引，现在还没用过，长见识了。

# Redis modules API
* [Introduction to Redis modules](https://redis.io/topics/modules-intro) Reids 的第三方插件？
* [Implementing native data types](https://redis.io/topics/modules-native-types) modules对原生数据类型的操作？

...

# Tutorials & FAQ
* [Introduction to Redis data types](https://redis.io/topics/data-types-intro) Redis的数据类型
* [Writing a simple Twitter clone with PHP and Redis](https://redis.io/topics/twitter-clone) 用 Redis 和 PHP 写一个 Twitter 客户端
* [Auto complete with Redis](http://autocomplete.redis.io/) 自动补齐
* [Data types short summary](https://redis.io/topics/data-types) 数据类型简介
* [FAQ](https://redis.io/topics/faq) 常见问题列表

# Administration
* [Redis-cli](https://redis.io/topics/rediscli) Redis 客户端命令
* [Configuration](https://redis.io/topics/config) Redis 配置
* [Replication](https://redis.io/topics/replication) 设置主从复制
* [Persistence](https://redis.io/topics/persistence) 持久化策略 RDB 和 AOF
* [Redis Administration](https://redis.io/topics/admin) 安装和配置时的一些注意点
* [Security](https://redis.io/topics/security) 概述Redis的安全
* [Encryption](https://redis.io/topics/encryption) 通信加密方案：一个第三方方案
* [Signals Handling](https://redis.io/topics/signals) 一些操作系统的信号
* [Connections Handling](https://redis.io/topics/clients) 原生 TCP 链接。
* [High Availability](https://redis.io/topics/sentinel) Redis Sentinel 解决 HA。








* []()
* []()
* []()
* []()
