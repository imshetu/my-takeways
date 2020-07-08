### Key characteristics of distributed system
* [Scalablity](#scalability)
* [Reliability](#reliability)
* [Availablity](#availability)
* [Efficiency](#efficiency)
* [Serviceability or Manageability](#manageability)

#### Scalability <a name="scalability"></a>
<hr/>
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


#### Reliability <a name="reliability"></a>
<hr/>
Reliability is the probability of a system  will fail in a given period. A system is considered to be reliable if it's keep delivering its services even after one or more software or hardware components fail. Reliability is one of most important characteristics of distributed system as the failing machine could be replaced by an healthy machine which ensures the completion of requested task. 

For example, an e-commerce website like Amazon does not want to lose the transactional information of a customer. Like when a customer puts an item to his/her cart, it has to be ensured that the item didn't go missing. In this case the failing machine has to be replaced with a healthy machine that has the exact information of the customer cart.


#### Availability <a name="availability"></a>
<hr/>
Availabilty is the time a system remain operational to perform it's required function in a specific time period. It is the measure of the system remain operational. 
For instance, an aeroplane that flows from one country to another carrying passenger is said to be available. Availability also take into account maintainabilty, repair time. An aeroplane that is down for maintainence is said to be unavailable.

Reliability is the availability over time considering the real world scenrio with all possible outcomes. An aeroplane that can carry passenger through all weather condition is to be considered reliable over an aeroplane that simply carrying passengers.

##### Reliability vs Availability
A reliable system is available but an available system might not be reliable. Let's say an e-commerce website that operates without any testing might be available 99.99% of the time with redundancy and monitoring but no way this system is reliable. 

If someone hacks this website and take some components down, then it will also lose its availability as well as its reliablity which eventually raise the issue of customer dissatisfaction.

#### Efficiency <a name="efficiency"></a>
<hr/>
Efficiency of any distributed system is generally measured by two factors.

* Latency - Response time of the system to get the first item
* Bandwidth - Throughput of the system in unit time. 

The bandwidth of the system can be broken two into two more metrics

* Number of messages sent by the system in a given amount of time irrespective of message size
* Size of messages in that window


The efficiency of a distributed system can be defined as a cost function of any of the metric above. But it would be overly simplistic. Because it does not take into account of the complext topography, architecture and heterogenity of machines that are deployed.

In reality it's very tough to determine the efficiency by taking all these into account instead we settle down for rough estimates of those metrics.

#### Serviceablity or Manageability <a name="manageability"></a>
<hr/>

Serviceablity or Manageability is the simplicity or speed with which a system can be maintained or repaired. If the system takes to much time to fix, then the availability of the system decreases. 

This also takes into account the time needed to diagnose or troubleshoot the issues arised. Early detection and monitoring can be helpful in this regard.