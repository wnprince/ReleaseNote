# Scalability

## What is Scalability

Scalability means the ability of the application to handle and withstand increased workload without sacrificing latency. If an app takes x seconds to respond to a user request, then it should to the same to each of the million concurrent user request on the application. The backend should not crumble under the load of millions of concurrent requests. It should scale well when subjected to a heavy traffic load and should maintain the latency of the system.

![](./media/scale.jpg)

### Latency

Latency is the amount of time a system takes to respond to a user request. Let's say you send a request to a server, and the server responds back in 2 seconds. In this case, the latency is 2 seconds. Software systems strive for minimum latency.

Latency is measure as the time difference between the action or  event triggered by the user and the response sent back to the user. It is generally divided into two parts:-

1. Network Latency
2. Application Latency

Network Latency is the amount of time the network takes to send a data packet from point A to point B. The network The network should be efficient enough to handle the increased traffic load on the website. To cut down the network latency, businesses use CDN & try to deploy their servers across the globe as close to the end-user as possible.

Application Latency is the amount of time the application takes to process a user request. There are more than a few ways to cut down the application latency. The first step is to run stress & load tests on the application & scan for the bottlenecks that slow down the system as a whole.

## Types of Scalability

There are two ways to scale an application:-

- Horizontal Scaling
- Vertical Scaling

### Vertical Scaling

Vertical scaling means adding more power to your server. let's say your app is hosted by a server. let's say your app is hosted by a server with 16 GB RAM. To handle increased load, you increase the RAM to 32 GB. You have vertically scaled your server. Ideally, when the traffic starts to build up, the first step should be to scale vertically. Vertical scaling is also known as scaling up.

It is the simplest way to scale as we just have to increase the power of hardware running the app. But there is a limit to the capacity we can augment for a single server.

### Horizontal Scaling

Horizontal scaling involves adding more hardware resources pool. This increases the computational power of the system as a whole. The increased traffic influx can be easily dealt with the increased computational capacity & there is literally no limit to how much we can scale horizontally assuming we have infinite resources. Horizontal scaling also provides us with the ability to dynamically scale in real-time as the traffic on our website increases & decreases over a period of time as opposed to vertical scaling which requires pre-planning & a stipulated time to be pulled off.

### Cloud Elasticity

The biggest reason why cloud computing got so popular is due to its ability to scale up and down dynamically. If the site has heavy influx, more server nodes get added dynamically, and when the influx goes low, dynamically added nodes are removed. This approach saves a lot of money for businesses on a daily basis.

### Pros and Cons

Vertical Scaling is a simpler approach compared to horizontal scaling as it does not require changing the code or system configuration. It takes much less administrative, monitoring and management efforts. But on the other side, vertical scaling is prone to availability risk. 

## Bottlenecks that hurt the Scalability of the Application

### Database

Usually, the entire application run on multiple nodes but the database runs on a single monolith, and has to serve all request coming from each node. This is a bottleneck and could result in high latency. Database also need to be scaled well, using methods like database partitioning, sharding or using multiple databases.

### Application Architecture

A poorly designed application’s architecture can become a major bottleneck as a whole. A common architectural mistake is not using asynchronous processes & modules where ever required rather all the processes are scheduled sequentially. Tasks such as uploading a document, sending confirmation email etc. should be done asynchronously.

### Using  Cache

Caching can be deployed at several layers of the application & it speeds up the response time by notches. It intercepts all the requests going to the database, reducing the overall load on it. Use caching exhaustively throughout the application to speed up things significantly.

### At Code Level

Avoid unnecessary loops, nested loops, tightly coupled code, using synchronous code causes bottlenecks to scalability.

## Tuning Performance of the Application

To improve the application's performance, following can be done:-

- Profiling - Run application profilers to check which processes are taking long and using too much resources.
- Caching - Use Cache. Cache all static content. Try to serve all read request from the cache.
- CDN - Using a CDN further reduces the latency of the application due to the proximity of the data from the requesting user.
- Compress data - Compressed data uses less bandwidth and download speed of the data on the client will be faster.

