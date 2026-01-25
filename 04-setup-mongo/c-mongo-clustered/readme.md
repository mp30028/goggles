## What is a MongoDb replica-set

A replica-set is cluster of MongoDb instances, also known as nodes, that contain identical copies of the data in order to provide high availability. This means if one of the nodes fail the others pick up the load whilst the failed node recovers.

![mongodb-cluster](./_assets/01-mongodb-cluster.png)  

This example will create a secure MongoDb cluster with three nodes incrementally step by step.

## Startup MongoDb networked instances
Start three instances of MongoDb each running in a docker container of it's own but arranged so that all three containers are in the same Docker network. Use the ***create-mongo-networked-instances.yml*** docker-compose file for this.  

The three instances are not yet configured to be in a cluster or secured.  

 ![starting-mongo-networked-instances](./_assets/02-starting-mongo-networked-instances.png)  
 
 

