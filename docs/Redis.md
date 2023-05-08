# Scaling with Redis Cluster
> https://redis.io/docs/reference/cluster-spec/
> https://redis.io/docs/management/scaling/
> https://redis.io/docs/reference/cluster-spec/#hash-tags

- Horizontal scaling with Redis is called a Redis cluster.
- High performance and linear scalability up to 1000 nodes. There are no proxies, asynchronous replication is used, and no merge operations are performed on values
- Redis cluster requires 2 ports to be open at every node
	- TCP Port: Default 6379
	- Cluster Bus Port: Default 10000 + TCP port = 16379
- To use Redis cluster on a single machine, we can use docker to map the ports such as all nodes internally run at the same ports while externally expose another set of ports
- Redis is, mostly, a single-threaded server from the POV of commands execution (actually modern versions of Redis use threads for different things). It is not designed to benefit from multiple CPU cores. People are supposed to launch several Redis instances to scale out on several cores if needed. It is not really fair to compare one single Redis instance to a multi-threaded data store

#### Redis cluster data sharding

> Redis cluster doesn't use consistent hashing. Instead uses **hash slot**

- There are 16384 hash slots in Redis Cluster, and to compute the hash slot for a given key, we simply take the [CRC16](https://en.wikipedia.org/wiki/Cyclic_redundancy_check) of the key modulo 16384.
	- CRC = Cyclic redundancy check
- Redis Cluster supports multiple key operations as long as all of the keys involved in a single command execution (or whole transaction, or Lua script execution) belong to the same hash slot. The user can force multiple keys to be part of the same hash slot by using a feature called _hash tags_.
	- the keys `user:{123}:profile` and `user:{123}:account` are guaranteed to be in the same hash slot because they share the same hash tag.
	- More on hash tags: https://redis.io/docs/reference/cluster-spec/#hash-tags

#### Redis Cluster master-replica model

When the cluster is created (or at a later time), we add a replica node to every master, so that the final cluster is composed of A, B, C that are master nodes, and A1, B1, C1 that are replica nodes. This way, the system can continue if node B fails.

Node B1 replicates B, and B fails, the cluster will promote node B1 as the new master and will continue to operate correctly.

However, note that if nodes B and B1 fail at the same time, Redis Cluster will not be able to continue to operate.

#### Redis Cluster consistency guarantees

- Redis Cluster does not guarantee **strong consistency**. In practical terms this means that under certain conditions it is possible that Redis Cluster will lose writes that were acknowledged by the system to the client.
- The first reason why Redis Cluster can lose writes is because it uses asynchronous replication
- Basically, there is a trade-off to be made between performance and consistency.
- Redis Cluster has support for synchronous writes when absolutely needed, implemented via the [`WAIT`](https://redis.io/commands/wait) command.
	- This makes losing writes a lot less likely. However, note that Redis Cluster does not implement strong consistency even when synchronous replication is used: it is always possible, under more complex failure scenarios, that a replica that was not able to receive the write will be elected as master.
- This amount of time is a very important configuration directive of Redis Cluster, and is called the **node timeout**.

## Redis Cluster configuration parameters