# Different Tiers in Software Architecture

## What is a Tier

A Tier is a logical separation of components in an application. Here, components means the various components of application like database, server, UI, etc.

The different components that make up a web service are displayed in the image below:-

![](D:\Notes\System Design\Software Architecture 101\media\WAA.jpg)

The different tiers of applications include:-

- Single Tier
- Two Tier
- Three Tier
- N Tier

## Single Tier

A single-tier application is an application where the user interface, backend business logic and the database, all reside in the same machine. Typical examples if a single tier application include MS Office or PC Games.

![](D:\Notes\System Design\Software Architecture 101\media\STA.jpg)

### Advantages

- No network latency since all the components are located on the same machine.
- No data request to the backend, which would make the ux slow.
- Data safety at the highest level since no data is transmitted over the network.

### Disadvantages

- Business will have no control over the application once the software is shipped due to which code or feature changes can't be done until customer manually updates the software.
- The code of single-tier application is vulnerable to being tweaked and reverse engineered.

## Two Tier

Two -tier applications consist of a *client*  and a *server*. The client would contain the user interface and business logic in one machine and a backend server would consist of a database running on different machine.

![](D:\Notes\System Design\Software Architecture 101\media\TTA.jpg)

### Why Two Tier Application

With two tier architecture, a question arises why the business logic is hosted on the client machine. The user can access the business logic and that might harm the business as the functionality could be reverse engineered.

The question is legit but there are use cases where two tier architecture might come in handy, for example, in to-do list app. In this case, it wouldn't cause significant business harm ever is the code is accessed by the third person as the logic is common and nothing proprietary. The upside to this would be that there are fewer network calls which will result in lower application latency. The app make calls to database only when some data has to be persisted, in this case, when a to-do has to be saved.

## Three Tier

Three-tier applications are most widely used in the industry. It consist of a user interface, backend server and a database all of which lie on different machines. They are physically separated.

![](D:\Notes\System Design\Software Architecture 101\media\3TA.jpg)

So, if we take a blog website as an example, the UI would be written in HTML, CSS and JavaScript, the backend would run on a server like apache or nginx and the database would be a MySQL. A three tier architecture works best for simple use-cases.

## N-Tier

An N-Tier application is an application which has more than three components involved. The components in an N-Tier Application include:-

- Cache
- Message queues for asynchronous behavior
- Load balancer
- Search servers for searching through massive amounts of data
- Components involved in processing massive amounts of data
- Components running heterogeneous tech commonly known as web services etc.

## Why do we have so many Tiers?

Two software design principles ae key to explaining this - Single Responsibility Principle and Separation of Concerns.

### Single Responsibility Principle

This principle means giving just one responsibility to a component and letting it execute it with perfection. This approach gives us a lot of flexibility and makes management easier, since maintaining one component won't affect others.

### Separation of Concern

Separation of concerns kind of means the same thing, be concerned about your work only & stop worrying about the rest of the stuff. Keeping components separate makes the reusable. 

Different services can use the same database, the messaging server or any component as long as they are not tightly coupled with each other. Having loosely coupled components is the way to go. The approach makes scaling the service easy in future when things grow beyond a certain level.

