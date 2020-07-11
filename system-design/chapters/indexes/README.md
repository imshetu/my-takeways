## Indexes

* [What is index?](#what)
* [Library catalog example](#example)
* [How does index slow down application?](#problems)


### What is index? <a name="what"></a>
<hr/>

Indexes are well known when it comes to databases. Sooner or later at some point of database optimization there's a time when the database performance becomes no longer satisfactory. In this case, indexes are the one of first thing the people look for.

Indexes are used for faster searches to find our rows or records in table and created based on one or multiple columns from that table.

### Library catalog example <a name="example"></a>
<hr/>

Think of an library catalog. This generally contains four kind of information i.e: name of the book, name of author, published date, subject. There are generally two types of catalogs found in the library. One based on name of the book in sorted way and one sorted based on name of author. So one can easily choose one of this catalog and find out their expected book as they are sorted. 

Similarly indexes are the catalogs to the databases. They contains information on which columns is stored where in the database.

We can think indexes to be a table like datastructure that contains two columns. One the column we want to search on and another contains the location of records in that database.

### How does index slow down application? <a name="problems"></a>
<hr/>

An index can dramatically improve the read performances of the application but it severly impacts the write performances. 

Because now every write operation we have to run like update, delete, create will take twice the time. One to write the data itself and two update the indexes to have the correct location of the data.

If we are building an application that will be written heavily but accessed rarely, implementing index will slow down the whole application.