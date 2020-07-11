## Redundancy & Replication

* [Redundancy](#red)
* [Replicaiton](#rep)

### Redundancy <a name="red"></a>
<hr/>

Redundancy is the duplication of critical software components to increase reliability of the system during failure or crash. Say, we have a copy of file which is important key point for our application if the file is lost due to a crash, we will lose data. As losing data is seldom helpful, we can easily avoid this by keeping more than one copy to the servers. Redundancy removes the single point of failure from our architecture.

Redundancy allows us to switch back to our duplicate server in any unexpected case of crash or failure.

### Replication <a name="rep"></a>
<hr/>

Replication is a process of sharing information in between the redundant component to ensure availability, consistency and performances. 

Mostly RDBMS uses this frequently with a primary replica relationship. So the primary replica server gets all the updates and ripple down all the changes to its secondary replica. Every replica server will output an event saying the data replication is completes when replication finishes.