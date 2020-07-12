## SQL vs NoSQL

* [SQL](#sql)
* [NoSQL](#nosql)
* [Differences](#differences)
* [How to choose](#choose)

When it comes to saving the data from your application, database is one of primary resort that we sought first. There are two types of database SQL and NoSQL. These are fundamentally different on how they save and treat data but they do one job and they do it well which is saving data.

### SQL <a name="sql"></a>
<hr/>

SQL database saved the data to rows and columns in a tabular format. It is very useful when the data format does not change that much and most of the data points are pre determined. MySQL, Oracle, Postgresql are the most popular example of this.

### NoSQL<a name="nosql"></a>
<hr/>

NoSQL is very popular due to its flexible schema and performance. There are many ways that a NoSQL database handles data. 

* **Key Value Pair** - Data is saved as key value pair. Key is the attribute name and value is the arributes nominal or text value. Redis, Voldemort and Dynamo are the example of this type of database.

* **Document database** - In document database data is save as a document. Those same kind of document form a collections. Each document of the collection can have their own schema but in reality they more or less follow the same schema though not concrete in a collections. Example: MongoDB, CouchDB.

* **Column database** - In this database, we have columns families. Each record is inserted as the row. It's not mandatory to have all the column value for a row. Each row can have different column values. Example: HBase, Cassandra

* **Graph Database** - In this kind of database, data is stored as a graph. Each record is saved as `node`, the attribute of record is known as `properties` and `lines` denotes the relation in between `nodes`. Example: Neo4j, InifinteGraph

### Differences<a name="differences"></a>
<hr/>

|Criteria|Description|SQL|NoSQL|
|---------|---------|---------|---------|
|Storage||Data is saved as row and columns|Data is mostly saved as key/value pair, document wise|
|Schema||Fixed schema where all the columns are determined|No fixed schema. We can change the schema on the fly.|
|Query||SQL|Every database has his own UnQl|
|Scalability||Generally vertically scalable. It can also be scaled horizontally but complex.|Horizontally scalable easily.|
|Reliability|ACID: Atomaticity, Consistency, Isolation, Durability|Performance will be bit slow.|Sacrifices ACID for performance and scaling|


### How to choose<a name="choose"></a>
<hr/>

### SQL 

* When data schema does not change over time.
* We need data compliance for financial sites & e-commerce sites. 

### NoSQL

* Storing large data volumes often have little to no structure.
* Making most the cloud computing and storage.
* Rapid development where data schema is not agreed.