## Load Balancer

* [What is a Load Balancer?](#what)
* [Benefits of a Load Balancer](#benefit)
* [How a server is selected by Load Balancer?](#strategy)
* [Benefits of a Load Balancer](#benefit)


### What is a Load Balancer? <a name="what"></a>
<hr/>
Load balancer is one of the important components of a distributed system. A Load Balancer (LB) spreads out the traffice across a cluster of server to improve responsiveness and availability of systems, databases or websites. LB also keeps track of healthy server that can be added to resource pool. LB stop routing any traffic to any servers that are unhealthy and failing for some several reason.

A LB generally sits in between the client and cluster of servers that can handle incoming requests and route the traffice to healthy servers.

We can also use loadbalance in different layer of our distributed systems to ensure full flexibility. For instance

* A LB in between client and web server
* A LB in between web servers and application servers
* A LB in between application servers and databases

### Benefits of a Load Balancer? <a name="benefit"></a>
<hr/>

* User experience faster and uninterrupted service.
* Service provider experience less downtime and higher throughput.
* LB enables system administrator to handle incoming requests while decreasing the wait time of other users.
* Smart LB can do predictive analysis and take actions if necessary.
* System administrator has to deal with small number of failed components. 

### How a server is selected by Load Balancer? <a name="strategy"></a>
<hr/>
LB selects a servers in two steps.

* Finding out the servers that are healthy
* Applying an algorithm across a cluster of servers that can serve the requests.

Healthy servers are found out by LB by doing `health check` to servers. The server which does not respond to health check will be removed from the resource pool and no traffic will be routed.

After that one of the following algorithms are used.

* **Least connection method** - route to the server that has the least number of connections
* **Least response time** - route to the server that has the lowest response time
* **Least bandwith method** - route to the server that is handling least amount of throughput at this moment
* **Round Robin method** - in this method, the loadbalacer starts choosing a server from one end of the pool and going next. When it reaches the end, he starts over again.
* **Weighted Round Robin method** - it is same as the round robin method except you can add weightage to the machines so that traffic is more distributed to machines with different configurations
* **IP Hash** - route based on the hash of client's ip


### Redundant Load Balancer <a name="redundancy"></a>
<hr/>

Using LB is very helpful but it also introduces a single point of failure as this is the single source of traffic entering in our system. In this case, we can use a second LB which is same capability wise to the first LB and both the LB watch over each other health. So when any one of them detects any issue with the other health, the healthy one simply takes over.



