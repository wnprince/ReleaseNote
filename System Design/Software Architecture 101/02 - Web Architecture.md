# Web Architecture

## What is Web Architecture?

Web architecture involves multiple components like *database*, *message queue*, *cache*, *user interface* & all running in conjunction with each other to form an online service.

## Client Server Architecture

Client Server Architecture is the fundamental building block of the web. The architecture works on request-response model. The client sends a request to the server for information an the server responds with it. Every website works on client server architecture.

### Client

A client is the machine that holds the user interface. User Interface is the presentation part of our application. There are 2 types of client:-

- Thin Client
- Thick Client or Fat Client

#### Thin Client

A client that holds only the UI of the application is known as a thick client. A thin client does not hold any business logic, and for every action would make request to the server, something commonly seen in 3 tier architecture.

#### Thick Client

A thick client, on the contrary to the thin client holds some or all the business logic along with the business logic, a pattern commonly seen in 2 tier applications.

### Server

A server is a machine that primarily listens to the request coming for a client and returns a response to the client after executing the business logic based on the parameters provided in the request. Every service running online runs on a web server. Servers running a web application are known as application server. Other servers include:-

- File server
- Mail server
- Proxy server
- Virtual server

All the components of a web application need a server to run. Be it a database, a message queue, a cache or any other component. In modern application development, even the user interface is hosted separately on a dedicated server.

## Communication over HTTP Protocol

The client & the server have a *request-response* model. The client sends the request & the server responds with the data. If there is no request, there is no response.

The entire communication between client and server happens over the *HTTP* protocol. It is the protocol for data exchange over the World Wide Web. *HTTP* protocol is a *request-response* protocol that defines how information is transmitted across the web.

## Rest API

REST is acronym for Representational State Transfer. It is a software architectural style for implementing web services. Web services implemented using the REST architectural style are known as the RESTful web services. A REST API is an API implementation that adheres to the REST architectural constraints. 

REST API acts as an interface. The communication between the client and server happens over HTTP. REST API takes advantage of the HTTP methodologies to establish communication between the client and the server. REST also enables servers to cache the response that improves the performance of the app.

The communication between client and server is  a stateless process, which means that every communication is like a new one. There is no information carried from the previous communications. So every time client interacts with the backend, it has to send the authentication as well.

With the implementation of REST API, the client gets backend endpoints to communicate with. A backend endpoint is a URL of a service. These endpoints completely decouples the backend & the client code. Due to this decoupling of backend and client code, developers can create multiple client interfaces, all connecting to the same backend. Introducing more clients or modifying client code will have no effect on the backend functionalities. This means clients and backend service. 

## HTTP PUSH and PULL

There are two modes of data transfer between the client and sever. HTTP PUSH and HTTP PULL.

The default mode of transfer is the HTTP PULL mode. The client sends the request first. The client sends request to the server and server sends back the response. The client pulls data from the server and hence it is called HTTP PULL.

The client pulls data from server whenever it requires, and keeps doing it over and over again, to fetch the updated data. Now, every server request and the response sent back consumes bandwidth. Every hit on the server costs the business money and adds more load on the server. If the data does not update but client keeps sending request, since it is unaware of the fact that data is not updated, it would cause waste of resources and hence, it is not ideal. Excessive pulls have potential to bring down the server.

To tackle this problem, we have HTTP PUSH based mechanism. In this mechanism, the client sends a request for particular information to the server once, and after that, the server keeps sending updates to the client whenever they are available. This saves a lot of network bandwidth and cuts down the load on the server by notches.

## HTTP PUSH in detail

### Time To Live (TTL)

In the regular client-server communication, which is HTTP PULL, the time to live for each request is 30 to 60 seconds, varying from browser to browser. If the client does not receive a response within the TTL, browser kills the connection and the client and to resend the request. Open connection consume a lot of resources and there is a certain limit to the number of open connections a server can handle. If the connections do not close and new ones are opened, The server will run out of memory.

### Persistent Connection

If we are certain that the returning a response will take more time that the TTL, we can use a persistent connection instead of open connection between client and server. A persistent connection is a network connection between the client and the server that remains open for further requests and responses.

### Heartbeat Interceptors

I browser kill the connection after response is not returned by the server after TTL. To keep the connection alive, persistent connections use Heartbeat Interceptors. They are blank request responses between client and the server to prevent the browser from killing the connection.

These are resource intensive, compared to the HTTP PULL behavior. But in some use cases, the are vital to the feature of an application.

For instance, a browser-based multiplayer game has a pretty large amount of request-response activity within a certain time in comparison to a regular web application. It would be apt to establish a persistent connection between the client and the server from a user experience standpoint.

## HTTP PUSH based Technologies

Technologies that use HTTP PUSH mode for client server communication are:- 

- Web Sockets
- AJAX - Long Polling
- HTML5 Event Source API & Server Sent Events
- Streaming Over HTTP

### Web Sockets

Web Sockets are ideally preferred when persistent bi-directional data-flow is required between client and server. Web sockets run over TCP instead of HTTP and server can client can stay connected using web sockets for as long as they want. Typical use cases include chat messaging apps and real time social media streams.



