

# 瀚思安信
Job Description [http://hansight.com/hr.html](http://hansight.com/hr.html)  
## 职责
* 负责公司Linux环境下JAVA相关软件项目的开发工作
* 严格执行软件项目开发规范，各阶段按规定输出对应的文档及代码
* 严格执行公司质量管理方针
* 在项目的调研、开发及验收过程中，及时与用户沟通

## 需求
* 三年以上J2SE开发经验，可以灵活的使用Java进行多线程编程，并熟练使用Spring MVC, Spring AOP, Hibernate
* 掌握RESTful的相关框架(Jersey 或 Spring）
* 熟悉Flume, Solr API及SolrCloud，了解Hadoop生态系统（HDFS, Zookeeper），懂得分布系统的基本概念
* 熟练使用Eclipse，Linux，MySql
* 很强的自学能力并对新事物充满好奇
* 可以适应偶尔较大的工作压力
* 可以很好的阅读英文文档

## 一面
时间：20170707 下午  
Q: TCP的三次握手
```
你瞅啥？（SYN）
瞅你咋地？（SYN-ACK）
来咱俩唠唠。（ACK）
```
严肃的说是这样的，A和B通信，
```
A首先发一个报文给B，
B收到了并且回复了A（这个时候A知道连接成功了），
A在回复B的回复（这个时候B知道连接成功了）。
```
所以说这三次，一次都不能少。
建立连接后，TCP要求在目标计算机成功收到数据时发回一个确认（即 ACK）。如果在某个时限内未收到相应的 ACK，将重新传送数据包。如果网络拥塞，这种重新传送将导致发送的数据包重复。但是，接收计算机可使用数据包的序号来确定它是否为重复数据包，并在必要时丢弃它。相比来说，UDP就是随便发发就好了，例如同城交友，QQ视频什么的，用的就是UDP。

Q: 项目经历  
Tigase是基于XMPP的开源实现，基于TCP的长连接，能支持的最大连接数取决于机器内存，模拟百万连接需要用到虚拟IP。

Q: 使用工具的技术细节  
DataX是一个在异构的数据库/文件系统之间高速交换数据的工具。

Q: RPC框架  
阿里有hsf、dubbo、Facebook有thrift、Google有grpc、Twitter有finagle、途牛有TSP。中间涉及到的技术有Java代理、序列化、java nio、mina、netty、zookeeper。

Q: zookeeper 的选举机制  
超过半数同意。

Q: 热部署  
动态拉起容器的技术，没太懂，是想问Docker？如果不清楚对方的问题是什么，以后要直接问出来。

Q: NIO  
当我们再讨论同步，异步，阻塞，非阻塞的时候，我们在讨论什么？

Q: 锁  
读锁、写锁
公平锁、非公平锁
乐观非乐观

Q: ConcurrentHashMap 如何保证线程安全？  
HashTable容器使用synchronized来保证线程安全，但在线程竞争激烈的情况下HashTable的效率非常低下。ConcurrentHashMap锁的粒度细一点，分段锁。

Q: Message Queue  
常见的MQ产品有kafka、rabbitmq、activemq。

Q: 算法题  
找出两个大文件里相同的记录，
遍历两个文件，hash(记录)%1000
到这1000个小文件里去找相同的。

## 二面
时间： 20170713 上午  
react 模式，线程是否越多越好，问的是线程阻塞问题
对无状态的理解 时序性的破坏也是破坏了状态  
JVM的堆栈、计数器的作用  
不能上网，如果一步步定位问题在哪？防火墙，vpn，dns什么的  
