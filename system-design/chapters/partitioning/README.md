## Data Partitioning

* [What is data partitioning?](#what)
* [Partitioning Method](#method)
* [Partitioning Criteria](#criteria)
* [Common problems of partitioning](#problems)


### What is data partitioning? <a name="what"></a>
<hr/>
Data partition is a technique which breaks down a large database into multiple databases. It is a process of breaking database into smaller databases that can be hosted in multiple machines for improving manageability, performance, availability and load balancing to redirect requests. In reality, at certain point of scaling, adding more servers becomes more feasible that adding beefier servers.

### Partitioning Method <a name="method"></a>
<hr/>
There are several type of partitioning method. Here we will see the most popular ones.

#####Horizontal paritioning
In this partitioning method we store rows to a table based on a range. For example let's think about we like to store places in a table. So we will keep places of a zip code in one table and one in other. Horizontal partition is also known as data sharding. 

The main problem of sharding is that it often creates unbalanced tables where one table with be read more than the others if the records are not distributed uniformly over the range.

#####Vertical partitioning
We can store also save a specific set of features into to different database in different servers. This is called vertical partitioning. For instance, let's consider we are designing instagram. We can easily store our user information to a database, post information in another and dedicate a separate database for photos of the users.

But often this kind of parititioning also requires another set of partitioning under this. Because it won't be a good idea to query among 10 billion of photos from 140 million of users in a table. 

##### Directory based partitioning
Directory based partitioning actually address the problems stated above. In here we simple keep a directory server that will hold the information which data actually stored in which server. After getting this information we can directly query that server for additional information about that resource. 

Though from the view point of scaling this method might looks lucrative because we will simply add server and update our directory server to adjust it. But one key point to observe by doing this we are introducing a single point of failure in our system. Because if the directory server fails then all our database connection is gone.


### Partitioning Criteria<a name="criteria"></a>
<hr/>
The parition criteria on which the records will be partitioned are described below.

##### Key or Hash based partitioning
The server on which the data will be determined by a hash function to any attribute of the servers. Let's say we have 100 servers so if we want to save the record `i` we can do a hash of `(i mod 100)`. This will give us a number on which our record can be saved.

The main problem of this approach is the number of servers play a vital role in this. So by adding a server more to our resource pool will actually outdate all our record. So we need to update our hash function and re-partition all our records again. And all this requires downtime of our system and has to be done as soon as we update our resource pool. But to overcome this we have a method called `Consistent Hashing` which will be discussed later.

##### List based partitioning
In this method we define a list with possible values of our records. For examples let's say we want to store the user information. In list based paritition could be if a user is from Britain, France, Germany or Belgium then we will save the user information to European database of our users.

##### Round Robin partitioning
In this method we will simply send our data to `i mod n` partition where n is the number of partition and i is the record. This ensures the uniform distribution of our records

##### Combined partitioning
Combined partitioning actually combines any approaches of the above. For example, we can first do list based partition on our record and then a hash based partition to select where our data will be stored. In fact, consistent hashing is one of the primary example of combined partitioning.

### Common problems of partitioning<a name="problems"></a>
<hr/>

##### Joins
Though partitioning looks very lucrative on the outside it actually gets complex when we want to do database operation. If data is partitioned then a join operation in between two partitioned table could be hectic because data from multiple servers has to be compiled and it becomes non-performant. So most of the database does not allow joining across table in different database. 

But we can easily denormalize the data to have all the join outputs in a single database but on that case we need to bear the problems of `Denormalization` which is data inconsistency in most cases. 

##### Referential Integrity
As most RDBMS doesn't allow foreign keys across databases in different servers which means referential integrity has to be maintained in application code. So a time to time SQL queries will have to be run to remove dangling references.

##### Rebalancing
We can always rebalances our database for the following issues

* The data distribution is not uniform
* A partition has to deal with extreme load

But rebalancing data is tedious and requires downtime. In this case Directory based partition might come in handy but it also adds a single point of failure in return.