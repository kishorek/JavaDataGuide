- [Distributed Computing](#distributed-computing)
- [Basic Principles](#basic-principles)
- [Decentralized vs. distributed](#decentralized-vs-distributed)
- [CAP Theorem](#cap-theorem)
- [BASE Theory](#base-theory)
- [Categories](#categories)
  - [Distributed Storage](#distributed-storage)
  - [Distributed Computing](#distributed-computing-1)
  - [Distributed Messaging](#distributed-messaging)
  - [Distributed Transactions](#distributed-transactions)

## Distributed Computing
When a group of computers working together to project as a single end system, it could be called as distributed system. These group of computers can have shared state, operate concurrently and fail independently without affecting the entire system. 

Distributed System enables horizontal scaling (i.e adding more computers to scale out). Vertical scaling is adding up more resources to the same server which has its resource limits and are potentially expensive. Other benefits are **Low Latency** (Since the cluster of machines can be geographically separated, requests can be served by the nearest ones which in turn reduces the Round-Trip Time) & **Fault Tolerance** (Even if one or more machines fail, the other machines in the cluster can keep the entire application up).



## Basic Principles


## CAP Theorem
Consistancy - Availability - Partition Tolerance
[Insert image here]

CAP theorem states that a distributed data store cannot simultaneously be consistent, available, and partition-tolerant.

-  Consistency - The data written to the store, should be available as soon as we read.
-  Availability - Even if a single node fails, other nodes will keep the whole system alive.
-  Partition Tolerance - The system continues to function and uphold its consistency/availability guarantees, in spite of network partitions.

## BASE Theory
- Basically Available — The system always returns a response.
- Soft state — The system could change over time, even during times of no input (due to eventual consistency).
- Eventual consistency — In the absence of input, the data will spread to every node sooner or later — thus becoming consistent.
- 
## Categories

### Distributed Storage

Most of the distributed databases are NoSQL non-relational databases (key-value store). They provide incredible performance and scalability at the cost of consistency or availability.

Some distributed databases that prefer eventual consistency: **Cassandra, Riak, Voldemort**
Some distributed databases that prefer stronger consistency: **HBase, Couchbase, Redis, Zookeeper**

[Visual Guide to NoSQL Systems](https://blog.nahurst.com/visual-guide-to-nosql-systems)

**Consensus**:
Consensus involves multiple nodes/servers agreeing on values. This is actually tricky and there are consensus algorithms that can help taking decisions

### Distributed Computing

### Distributed Messaging
### Distributed Transactions

Ref: [A Thorough Introduction to Distributed Systems](https://medium.com/better-programming/a-thorough-introduction-to-distributed-systems-3b91562c9b3c)