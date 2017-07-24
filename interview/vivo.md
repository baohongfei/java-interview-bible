# VIVO
一面  
时间 20170722 周六下午  

# Netty  
简单介绍一下Netty  
Reactor模式+事件驱动+异步非阻塞IO+多线程模型  
[Netty线程模型](http://www.infoq.com/cn/articles/netty-threading-model)  
[深入研究Netty框架之ByteBuf功能原理及源码分析](https://my.oschina.net/7001/blog/742236)  
ByteBuf 动态扩展通常情况下，当对JDK ByteBuffer进行put操作时，如果缓冲区可写空间不够，就会抛出BufferOverflowException异常。为了避免这个问题，在进行put操作时，需要对可写空间进行判断，如果剩余可写空间不足，需要创建一个新ByteBuffer，并将之前ByteBuffer的内容复制到新创建的ByteBuffer中，然后释放老的ByteBuffer。  
零拷贝  
ChannelOption的TCP_NODELAY属性设置  

# MySQL  
## 索引失效的场景  
查询条件包含or  
组合索引，不是使用第一列索引，索引失效 索引的最左匹配特性。  
like 以%开头  
如果列类型是字符串，where时一定用引号括起来，否则索引失效  
当全表扫描速度比索引速度快时，mysql会使用全表扫描，此时索引失效  
不适合键值较少的列（重复数据较多的列）  
not in ,not exist !=.  
对索引字段进行计算  
在ORDER BY操作中，排序的列同时也在WHERE中时，MYSQL将无法使用索引  
如果某个数据列里包含着许多重复的值，就算为它建立了索引也不会有很好的效果  
索引不存储null值  

## SQL 优化和慢查  
[MySQL索引原理及慢查询优化](https://tech.meituan.com/mysql-index.html)  
建索引的几大原则  
1. 最左前缀匹配原则，非常重要的原则，mysql会一直向右匹配直到遇到范围查询(>、<、between、like)就停止匹配，比如a = 1 and b = 2 and c > 3 and d = 4 如果建立(a,b,c,d)顺序的索引，d是用不到索引的，如果建立(a,b,d,c)的索引则都可以用到，a,b,d的顺序可以任意调整。
2. =和in可以乱序，比如a = 1 and b = 2 and c = 3 建立(a,b,c)索引可以任意顺序，mysql的查询优化器会帮你优化成索引可以识别的形式
3. 尽量选择区分度高的列作为索引,区分度的公式是count(distinct col)/count(\*)，表示字段不重复的比例，比例越大我们扫描的记录数越少，唯一键的区分度是1，而一些状态、性别字段可能在大数据面前区分度就是0，那可能有人会问，这个比例有什么经验值吗？使用场景不同，这个值也很难确定，一般需要join的字段我们都要求是0.1以上，即平均1条扫描10条记录
4. 索引列不能参与计算，保持列“干净”，比如from_unixtime(create_time) = ’2014-05-29’就不能使用到索引，原因很简单，b+树中存的都是数据表中的字段值，但进行检索时，需要把所有元素都应用函数才能比较，显然成本太大。所以语句应该写成create_time = unix_timestamp(’2014-05-29’);
5. 尽量的扩展索引，不要新建索引。比如表中已经有a的索引，现在要加(a,b)的索引，那么只需要修改原来的索引即可

varchar等值比较没有写单引号  
[8.2.1.1 WHERE Clause Optimization](https://dev.mysql.com/doc/refman/5.7/en/where-optimization.html)  

InnoDB的聚簇索引与第二索引  
MySQL 里的数据类型  
DATE、DATETIME、TIMESTAMP 类型的区别  
最主要的区别-受时区影响不同。timestamp会跟随设置的时区变化而变化，而datetime保存的是绝对值不会变化。  
占用存储空间不同。timestamp储存占用4个字节，datetime储存占用8个字节  
可表示的时间范围不同。timestamp可表示范围:1970-01-01 00:00:00~2038-01-09 03:14:07，datetime支持的范围更宽1000-01-01 00:00:00 ~ 9999-12-31 23:59:59  
索引速度不同。timestamp更轻量，索引相对datetime更快。  

数据库的表设计  
行锁 表锁  
[Innodb中的事务隔离级别和锁的关系](https://tech.meituan.com/innodb-lock.html)

# HTTP  
消息头有哪些？  
Referer头的作用。

# HTTPS  
建立链接的过程  

# Spring  
Spring 的最基础配置包括哪些  
SpringMVC 对一条请求的处理流程  

# 并发
## AQS 的实现原理  
## CAS 的实现  
[JAVA CAS原理深度分析](http://zl198751.iteye.com/blog/1848575)
[Java CAS 理解](https://mritd.me/2017/02/06/java-cas/)
ABA问题  
