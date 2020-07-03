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

-  **C**onsistency - The data written to the store, should be available as soon as we read.
-  **A**vailability - Even if a single node fails, other nodes will keep the whole system alive.
-  **P**artition Tolerance - The system continues to function and uphold its consistency/availability guarantees, in spite of network partitions.

## BASE Theory
- **B**asically **A**vailable — The system always returns a response.
- **S**oft state — The system could change over time, even during times of no input (due to eventual consistency).
- **E**ventual #consistency — In the absence of input, the data will spread to every node sooner or later — thus becoming consistent.

## Categories

### Distributed Storage

Most of the distributed databases are NoSQL non-relational databases (key-value store). They provide incredible performance and scalability at the cost of consistency or availability.

Some distributed databases that prefer eventual consistency: **Cassandra, Riak, Voldemort**
Some distributed databases that prefer stronger consistency: **HBase, Couchbase, Redis, Zookeeper**

[Visual Guide to NoSQL Systems](https://blog.nahurst.com/visual-guide-to-nosql-systems)

**Consensus**:
Consensus involves multiple nodes/servers agreeing on values. This is actually tricky and there are consensus algorithms that can help taking decisions

### Distributed File Systems
Distributed file systems are just like distributed databases, storing and accessing large amount of data across cluster of machines. They compliment distributed computing.

**HDFS**
Hadoop Distributed File System (HDFS) is the distributed file system used for distributed computing via the Hadoop framework. It is used to store and replicate large files (GB or TB in size) across many machines.

This architecture contains NameNodes and DataNodes. NameNodes contains the metadata about the cluster and information about which data is stored where. DataNodes stores the data in blocks.

**IPFS**
Interplanetary File System (IPFS) is a peer-to-peer protocol/network for a distributed file system. Leveraging blockchain technology, it boasts a completely decentralized architecture with no single owner nor point of failure.

### Distributed Computing
Distributed computing is distributing the processing into multiple nodes/servers. i.e. Splitting an enormous task (which may be very difficult for a single system to process) in to multiple minor tasks and getting it processed by multiple computers. This approach will help to scale horizontally, when the task is bigger increase the nodes.

**MapReduce** :
MapReduce is a distributed computing programming model. As the name indicates, it performs 2 operations. Mapping (filtering and/or sorting) the data and reducing it into a final desired outcome. The "MapReduce System" orchestrates the processing, running the various tasks in parallel, managing all communications and data transfers between the various parts of the system, and providing for redundancy and fault tolerance.

Assuming the data is stored across multiple databases in a warehouse, there will multiple map jobs created to fetch data from its assigned database. Each map job will transform as much data as it can. Then Shuffle, Sort and Partition are done before the job is sent to appropriate reduce job.

MapReduce libraries are written in many languages. Most familiar one is Apache Hadoop. MapReduce is initially created by Google.

Other architectures that are becoming more popular like Lambda Architecture (performs both batch & stream processing). This has brought the new tools like Apache Kafka, Apache Storm, Apache Samza

### Distributed Messaging

### Distributed Transactions



Ref: [A Thorough Introduction to Distributed Systems](https://medium.com/better-programming/a-thorough-introduction-to-distributed-systems-3b91562c9b3c)