## Caching

* [What is caching?](#what)
* [Application Server Caching](#asc)
* [Content Distribution Network](#cdn)
* [Cache Invalidation](#invalidation)
* [Cache Eviction](#eviction)


### What is caching? <a name="what"></a>
<hr/>
While LB can distribute traffic across a cluster of servers, caching can help us take out the best performance out of our existing infrastructure. In reality caching is found in almost every level of our architecture be it website, applications, databases e.t.c. Caching work on locality of reference principle which means recently requested data likely to get requested again. A cache is like a short term memory much faster than our databases and has limited amount of space. Generally cache is applied to the layer that is closest to front end so that it can reduce the number of requests to our downstream levels.

### Application Server Cache <a name="asc"></a>
<hr/>
If caching is placed in a layer that handles the requests directly then it enables the local storage of response data. So when a request is arrived first it checks if the data is available in cache, if yes it returns from cache otherwise it will make a call to network storage to get the data and send it to client after caching it. Generally a cache in such node might be a short term memory or might be a local storage which will be faster than the actual network storage in terms of accessing the data.

Tha above works just fine when we talk about a server. But it comes to multiple servers connected to a load balancer then the whole thing becomes a bit tricky. So let's think all the server have their own local cache. If the LB randomly select the server to send the requests it will create many cache miss in the application server. In this type of scenario, we can think of a centralized cache or a distributed cache.

### Content Distribution Network <a name="cdn"></a>
<hr/>
Content Distribution Network (CDN) comes in handy when we are considering a large number of static content. So when a client requests for some resource in CDN, if it doesn't found in the CDN, it immediately requests the central server to get the resource, cache it by itself and serve it to the client.

But if the system design is not enough robust to need a CDN then it's always a good idea to cache them in a subdomain named `static` and serve it from there. This will allow the migration from DNS to CDN much easier.

### Cache Invalidation <a name="invalidation"></a>
<hr/>
While caching sounds very lucrative, it comes at a prices. We always need to update the cache to discard the invalidate one so that our system always get up-to-date data and works as expected.

Few techniques of cache invalidation are described below

|Name|Cache<br/>Time of writing|Database<br/>Time of writing|Pros|Cons|
|------------|------------|------------|------------|------------|
|Write Through Cache|Same|Same|<ul><li>Consistent</li><li>Both cache & database remain in sync</li></ul>|<ul><li>As the data will be returned after 2 write operations, it becomes slow in case of write heavy application</li></ul>|
### Cache Eviction <a name="evication"></a>
<hr/>