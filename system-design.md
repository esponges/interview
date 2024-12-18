## System Requirements

### Functional Requirements
Functional requirements describe what a system must do, or what its features and functions are. They define the system's behavior and how it should interact with users and other systems. Functional requirements are typically specified by business stakeholders and users.

### Non-functional Requirements
Non-functional requirements describe how a system should perform. They define the system's quality attributes, such as performance, security, reliability, usability, and maintainability. Non-functional requirements are typically specified by technical stakeholders, such as software developers and architects.

## Scalability
Scalability refers to the capability of a system to handle a growing amount of work, or its potential to perform more total work in the same elapsed time when processing power is expanded to accommodate growth. A system is said to be scalable if it can increase its workload and throughput when additional resources are added.

### Availability
Availability is the percentage of time that a system is operational and accessible to users. It is typically measured as a percentage of uptime over a given period of time. For example, a system that is available 99.9% of the time would be considered highly available.

### Consistency
Consistency refers to the state of a system's data. A system is considered consistent if all users see the same data at the same time. For example, if a user updates a record, all subsequent requests should see the updated record.

### Partition Tolerance
Partition tolerance refers to a system's ability to continue to operate despite partial system failure or loss of network connectivity. A system that is partition tolerant can sustain any amount of network failure that doesn't result in a failure of the entire network.

### CAP Theorem
The CAP theorem states that it is impossible for a distributed data store to simultaneously provide more than two out of the following three guarantees:

- Consistency: Every read receives the most recent write or an error.
- Availability: Every request receives a (non-error) response, without the guarantee that it contains the most recent write.
- Partition tolerance: The system continues to operate despite an arbitrary number of messages being dropped (or delayed) by the network between nodes.

## API
An API (application promgramming interface) is a contract that defines how two applications interact with each other. APIs are typically used to allow applications to communicate with each other by sending and receiving data.
### Gateway
An API gateway is a server that acts as a single entry point for all requests from clients to the backend services. It provides a centralized place to define, publish, maintain, monitor, and secure APIs. It also provides additional cross-cutting features such as authentication, SSL termination, and rate limiting.

## API Design
### REST
REST stands for Representational State Transfer. It is an architectural style that defines a set of constraints to be used for creating web services. RESTful web services allow the requesting systems to access and manipulate textual representations of web resources by using a uniform and predefined set of stateless operations.

RESTful web services are stateless. This means that each request contains all of the information necessary for the server to understand and process it. The server cannot rely on any information that is stored on the client. This constraint allows RESTful applications to be highly scalable since they can be deployed on multiple servers and load balanced.

Advantages:
- Scalability
- Flexibility
- Simplicity

Disadvantages:
- Lack of standardization
- Security concerns

Use cases:
- Public APIs
- Web applications
- Mobile applications

### SOAP
SOAP stands for Simple Object Access Protocol. It is a messaging protocol that defines a set of rules for structuring messages that can be used for exchanging information between systems. SOAP messages are typically sent using HTTP (Hypertext Transfer Protocol) but can also be sent using SMTP (Simple Mail Transfer Protocol) or other protocols.

SOAP messages are XML documents that contain a set of rules for structuring messages. These rules define the structure of the message, the encoding scheme, and the conventions for representing remote procedure calls and responses.

Advantages:
- Standardization
- Security
- Extensibility

Disadvantages:
- Complexity
- Performance - slower than REST
- Lack of flexibility

Use cases:
- Enterprise applications
- Applications that require high security

### GraphQL
GraphQL is a query language for APIs and a runtime for fulfilling those queries with existing data. GraphQL provides a complete and understandable description of the data in your API, gives clients the power to ask for exactly what they need and nothing more, makes it easier to evolve APIs over time, and enables powerful developer tools.

Advantages:
- Flexibility
- Performance
- Strongly typed

Disadvantages:
- Caching
- Complexity
- Lack of standardization

Use cases (same as REST):
- Public APIs
- Web applications
- Mobile applications

### RPC
RPC stands for Remote Procedure Call. It is a protocol that allows a computer program to execute a subroutine or procedure on another computer without the programmer having to explicitly code the details for this remote interaction. RPC is a request-response protocol. 

A client sends a request to a server, and the server responds to the request. With RPC you call a function on a remote server as if it were a local function.

```typescript
// HTTP/REST
const res = await fetch('/api/users/1');
const user = await res.json();

// RPC
const user = await api.users.getById({ id: 1 });
```

Advantages:
- More complex operations
- No need for data transformation (JSON, XML, etc.)
- Very fast
- Strongly typed

Disadvantages:
- Complexity
- Not very flexible

## Databases
### Relational Databases
A relational database is a type of database that stores and provides access to data points that are related to one another. Relational databases are based on the relational model, which organizes data into one or more tables (or "relations") of columns and rows, with a unique key identifying each row. Rows are also called records or tuples.

Advantages:
- Data integrity
- Data consistency
- Data security
- Data independence

Disadvantages:
- Difficult to scale
- Difficult to change
- Difficult to maintain

Examples:
- MySQL
- PostgreSQL
- Oracle
- SQL Server

Use cases:
- Applications that require multi-row transactions
- Applications that require high security
- Applications that require complex queries

### Non-relational Databases
A non-relational database is a type of database that stores and provides access to data points that are unrelated to one another. Non-relational databases are based on the non-relational model, which organizes data into one or more collections of documents, with each document containing one or more fields. Documents can be thought of as the equivalent of rows in a relational database, and fields as the equivalent of columns.

Advantages:
- Scalability
- Flexibility
- Performance

Disadvantages:
- Data integrity
- Data consistency
- Data security

Examples:
- MongoDB
- Cassandra
- HBase - ideal for chat applications due to its high availability and low latency

Use cases:
- Applications that require high scalability
- Applications that require high performance
- Applications that require high availability

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

Main types of sharding:
- Hash-based sharding - uses a hash function to determine which machine should store a given piece of data. This approach is often used to distribute data evenly across multiple machines but it's not good for separating data that is related to each other.
- Range based sharding - uses a range of values to determine which machine should store a given piece of data. Eg. you could range-partition a database of customer data based on the customer ID, with each partition containing customers with IDs in a specific range. 
- Directory sharding - Directory sharding uses a lookup table to match database information to the corresponding physical shard. This approach is not limited by range but could fail if the lookup table contains incorrect information.
- Geographical sharding - uses the location of the user to determine which machine should store a given piece of data.

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

## Caching
Caching is a technique that stores copies of frequently accessed data in a location that is closer to the user or application. This can improve performance and scalability by reducing the number of requests that need to be made to the underlying database or other data source.

There are two main types of caching:

- In-memory caching: This type of caching stores data in memory, which is much faster than typical disk storage.
- Distributed caching: This type of caching stores data across multiple servers, which can improve scalability and reliability.

### In-memory Caching
In-memory caching stores data in memory, which is much faster than typical disk storage. This type of caching is often used to cache data that is frequently accessed by an application, such as user profiles or product information.

Advantages:
- Fast
- Easy to implement
- Easy to scale

Disadvantages:
- Data loss
- Limited by the amount of memory available
- Data duplication

### Distributed Caching
This type of caching stores data across multiple servers, which can improve scalability and reliability. Distributed caches are typically used to cache large amounts of data that need to be accessed by multiple applications or servers.

Advantages:
- Scalability
- Can store large amounts of data

Disadvantages:
- Complex to implement
- Slower than in-memory caching
- More expensive

When designing a system that uses caching, it is important to consider the following factors:

- What type of data will be cached?
> e.g. static content, dynamic content, etc.
- How often will the data be updated?
- How much data needs to be cached?
- How many applications or servers will need to access the cache?
- What is the budget for implementing and managing the cache?

### Popular Caching Solutions
For static content such as media, CSS, and JavaScript files:
- CDNs: CDN stands for content delivery network. CDNs are a network of servers that are distributed around the world. They are used to deliver content, such as web pages, images, and videos, to users with the lowest possible latency.

For dynamic content like db results, rendered pages, etc:
- Redis: Redis is an in-memory data structure store that supports key-value pairs, strings, lists, sets, sorted sets,hashes, geospatial indexes, hyperloglog, bitmaps, streams, and pub/sub.
- Memcached: Memcached is a distributed in-memory key-value store that is designed for speed and scalability.


### Caching Eviction Policies
Caching eviction policies are used to determine which items should be removed from the cache when it is full. There are several different types of eviction policies, including:

- Least Recently Used (LRU): This policy removes the least recently used items from the cache.
- Least Frequently Used (LFU): This policy removes the least frequently used items from the cache.
- First In First Out (FIFO): This policy removes the oldest items from the cache.
- Random: This policy removes random items from the cache.

## Monitoring
Monitoring is the process of collecting and analyzing data about a system to determine its health and performance. It is used to identify bottlenecks, detect failures, and improve the overall performance of a system.

Client and servers can be monitored using a variety of tools, including:
- Prometheus
- Grafana
- Datadog

## Load Balancing
Load balancing is the process of distributing workloads across multiple servers. It is used to improve the performance and reliability of a system by distributing the workload across multiple servers.

Load balancers can be implemented using a variety of techniques: Round Robin, Least Connections, Least Response Time, etc.

### Round Robin
Round Robin is a load balancing technique that distributes requests evenly across a set of servers. It is often used to distribute requests across multiple servers in a cluster. This technique is simple and easy to implement, but it _does not take into account the current load on each server_.

### Weighted Round Robin
Weighted Round Robin is a load balancing technique that distributes requests across a set of servers based on their weight. This technique is similar to Round Robin, but it takes into account the current load on each server. This technique is more complex than Round Robin, but it can be more effective at distributing requests evenly across a set of servers and it's advisable to use it _when the servers have different capacities_.

### Least Connections
Least Connections is a load balancing technique that distributes requests to the server with the least number of active connections. This technique is more complex than Round Robin, but it can be more effective at distributing requests evenly across a set of servers.



