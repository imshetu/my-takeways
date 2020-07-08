### Key characteristics of distributed system

#### Scalability
Scalability is known as the ability of a system, process or software to grow in order to meet increased demand. A system is known to be scalable when it can continuously evolve to support to growing amount of work.

A system may need to scale for the following reasons
* Increase in number of works
* Increase in data volumes
* Number of transactions

A scalable system can support all of the evolve without sacrificing its performance.

But the performance of the scalable system might decline with the growth of system size due to management and environmental issues. For instance, network speed might be low in between node due to placement of theirs. Also there might be some functions which are atomic in nature or some flaw in system design earlier that might also hinder the speed-up in distributed system

There are two types of scaling. Those are

|Scaling|Criteria|Example|
|---------|-----------|----------|
|Horizontal| Adding more servers to current resource pool. Doesn't require any downtime | Cassandra, CouchDB
|Vertical| Adding more resources to current server. Like adding memory to a server. Require downtime | Mysql
