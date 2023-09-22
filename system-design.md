## Scalability
Scalability refers to the capability of a system to handle a growing amount of work, or its potential to perform more total work in the same elapsed time when processing power is expanded to accommodate growth. A system is said to be scalable if it can increase its workload and throughput when additional resources are added.

## Database Scaling
### Vertical Scaling
The vertical scaling approach, sometimes referred to as "scaling up," focuses on adding more resources or more processing power to a single machine. These additions may include CPU and RAM resources upgrades which will increase the processing speed of a single server or increase the storage capacity of a single machine to address increasing data requirements.

Advantages:
- Less complex
- Less expensive
- Easier to maintain

Disadvantages:
- Limited by the capacity of a single machine
- Downtime during upgrades
- Difficult to scale dynamically

Suitable for:
- Small applications
- Applications with a small user base
- Applications with a small data set
- MySQL, Amazon RDS, PostgreSQL, Oracle, SQL Server (most of the relational databases)

### Horizontal Scaling
The horizontal scaling approach, sometimes referred to as "scaling out," focuses on adding more machines to the pool of resources that are available to the application. This approach is often used to address increasing traffic to an application by sharing the processing and I/O load across multiple machines.

Advantages:
- No downtime during upgrades
- Easier to scale dynamically
- No limit to the number of machines that can be added

Disadvantages:
- More complex
- More expensive
- More difficult to maintain

Suitable for:
- Large applications
- MongoDB, Cassandra, HBase

### Sharding
Sharding is a type of horizontal scaling that involves breaking up the data set and distributing it across multiple machines. This approach is often used to address increasing data requirements by sharing the data set across multiple machines.

Advantages:
- Improves system tolerance and availability since it has a single point of failure

Disadvantages:
- More complex to distribute evenly (do not cause imbalances) across machines
- More expensive
- Difficult to roll back to unsharded architecture

Suitable for:
- Large applications with a large data set
- High traffic applications that should handle lot of concurrent requests

### Replication
Replication is a type of horizontal scaling that involves creating multiple copies of the data set and distributing the copies across multiple machines. This approach is often used to address increasing traffic to an application by sharing the processing and I/O load across multiple machines.

Advantages:
- System availability and fault tolerance is greatly improved since there is no single point of failure
- More read operations can be performed since the data set is distributed across multiple machines which decreases the load on a single machine

Disadvantages:
- Risk of duplication -inconsistency- of data
- More complex to distribute evenly across machines
- More expensive

Suitable for:
- Read heavy applications that require high availability and performance
- Applications that need to scale dynamically
- Applications that need quick data recovery

### ACID
ACID stands for Atomicity, Consistency, Isolation, and Durability. These properties ensure that the data in a database is always in a consistent state, even if there are failures or concurrent transactions.

- Atomicity: All of the operations in a transaction must either succeed or fail together. There can be no partial failures.
- Consistency: Each transaction must leave the database in a consistent state. This means that all of the constraints on the data must be satisfied.
- Isolation: Transactions must be isolated from each other. This means that one transaction cannot see the uncommitted changes of another transaction.
- Durability: Once a transaction is committed, its changes must be durable. This means that the changes cannot be lost, even if there is a failure.

Depending on the applications needs, the ACID properties can be relaxed to improve performance. For example, a database may choose to relax the isolation property to improve concurrency, or it can tolerate some data loss to improve availability.
