### CAP Theorem

CAP theorem states that it is impossible for distributed software system to have simultaneously more than two of the three gurantees. 

* **Consistency** - All the node see data at the same time.
* **Availability** - Every response get either success/failure.
* **Partition tolerance** - The system remain functional even when one or more system component fails.

For example we can't even design a simple datastore that meets all the three properties mentioned above. For example we want our datastore to be consistent, available and partition tolerant. Let's say we want our system to be consistent that will need our data to be copied over all the redundancies. If one partition fails to update the data,  system will read from a out of date partition which means the data will not be consistent. That way we will lose the partition tolerance as the system can't function well without proper data.  On the other hand to make it partition tolerant, then we have to wait to respond till all the paritions are updated. In that case our datastore will not be available 100% of the time.