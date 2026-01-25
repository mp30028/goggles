# Running MongoDb

MongoDb can be run many ways. However to support an event driven architecture we need to run MongoDb as a replica-set.


## What is a MongoDb replica-set

A replica-set is cluster of MongoDb instances, also known as nodes, that contain identical copies of the data in order to provide high availability. This means if one of the nodes fail the others pick up the load whilst the failed node recovers.

![mongodb-cluster](./_assets/01-mongodb-cluster.png)  


## Incremental development of an orchestration solution of a secure MongoDb cluster 
These examples will develop step by step and incrementally a complete solution that will be a secure MongoDb cluster with three nodes.

### 1. Get Started with a single instance using direct docker command 
To get started run a single instance of MongoDb using a direct docker command as illustrated in [this example](./a-mongodb-with-docker-cmd/readme.md)

### 2. Startup MongoDb networked instances
Start three instances of MongoDb each running in a docker container of it's own but arranged so that all three containers are in the same Docker network. [See this example](./b-mongo-networked-instances/readme.md)
 
## [Home](../README.md)
 

