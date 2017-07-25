[https://zookeeper.apache.org/doc/current/](https://zookeeper.apache.org/doc/current/)  
# 选举策略
投票机制，跟现实中投票最大的不同是，节点会根据myid、zxid (ZooKeeper Transaction Id)规则，改变自己的意见。
# 脑裂
ZooKeeper 就提供了至少三种方式来认定整个集群是否可用，其中majority quorums 就是类似上面说的用结点个数限制的思想来实现的。即只有集群中超过半数节点投票才能选举出 master。这也是 ZooKeeper 的默认方式。还有两种一种是通过冗余通信，允许集群中采用多种通信方式来防止单一通信方式实效。另一种是通过共享资源，比如能看到共享资源就表示在集群中，反之则不是。  
