## Consistent Hashing

Distributed Hash tables are one of the key components in distributed system design. A Hash tables needs a key, value and a hash function. It return the key which maps the value of the hash function. In general
```
    key = hash_function(value)
```

But it does not works as expected in the following cases. 

Let's think we are building a distributed cache system for us. We will be using `i%n` as our hash_function where `n` is the number of servers and `i` be the record. This will fail for following reasons.

* When we add another server or remove one server then value of `n` changes which make all the value to be remapped for that cache.

* Once again as the data is not distributed so the hash mapping of it won't be uniform.


In this system, Consistent Hashing is a good way to handle this system.


Consistent Hashing states that if `k` be the number of keys and `n` be the number of servers on `k/n` number of entry has to be remapped in any case the value of `n` is changed.

So when a new server is added, it will take some of the entries from the adjancent severs keeping the other servers intanct. And if any server is removed from the pool then it distributes the keys to other servers.

Let's consider we have a [0, 256] size of servers which are sits in the circle. This is how consistent hashing is mapped.

* Find the hash of value to a single digit. 
* Then start clockwise traversal.
* The value will saved in the first server encounterd.
* When a server is introduced in between it will get the values instead of old server along the path.


To improve the unbalanced dataset in cache we can uniformly place the server in a interval so that multiple replica of a server can be found multiple times in the circle.