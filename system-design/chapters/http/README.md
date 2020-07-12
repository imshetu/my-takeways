## HTTP Connections

* [Ajax Polling](#ajax)
* [Long Polling](#long)
* [Websocket](#socket)
* [Server Sent Events](#sse)

### General HTTP Communication

* A client requests server for a request
* A server calcaluates the response and send back.
* The client process the response when it's returned.

### Ajax Polling <a name="ajax"></a>
<hr/>

* A client make periodic requests to servers for resource.
* A server process the requests.
* It sends an empty requests if resource not found. 
* The client process the requests when it's returned.

But main downfall of this approach that many HTTP request get wasted with similar response causing an HTTP overhead.

### Long Polling <a name="long"></a>
<hr/>

* A client make request to server.
* If the server were to send the empty resources, it does not send any response.
* Instead of this request, it keeps the connection open. 
* When the data is populated, it send the response to the server.
* Most of the time this incurs a long timeout before calling the http again.


### Websockets <a name="socket"></a>
<hr/>

* Websocket supports the full duplex connection.
* Once the connection is established between the client and server, both can commnunicate and send data between themselves.

### Server Sent Events <a name="sse"></a>
<hr/>

* The client first establish a connection to the server.
* From that point the server constantly updates the client with new data if theres any.
* If client is to send data to server they had to adopt new protocol for this.
* Often useful when we want real-time traffic updating our clients

