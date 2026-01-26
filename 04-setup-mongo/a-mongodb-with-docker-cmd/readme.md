## Setting up MongoDb

### 1. Run a simple setup of the latest version

  **i.** Find the latest version of mongodb docker image  
  [MongoDb tags on docker hub](https://hub.docker.com/_/mongo/tags)

  **ii.** Pull the image using the selected tag 
  `docker pull mongo:8.2.3`

  **iii.** Startup a container using the image  
  `docker run --name mongo-test -p 27017:27017 -d mongo:8.2.3`
   
  **iv.** Shell into the container  
  `docker exec -it mongo-test bash`
  
  **v.** Run the mongo client, mongosh, from the command prompt in the container  
  `mongosh`
  
  ![Command prompt trace](./_assets/01-running-simple-mongo-setup.png)
  

### [Back](../readme.md)