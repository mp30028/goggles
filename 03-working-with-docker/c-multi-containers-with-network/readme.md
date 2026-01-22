## Run multiple containers with Docker Compose within a docker network


### 1. Start up the containers
  
  `docker compose -f .\multi-containers-with-net.yml up -d`  
  
  To stop the instance started with docker-compose run `docker compose -f .\multi-containers-with-net.yml down`
  
### 2. Setup permission and password for the root login
  Follow steps 2 to 8 [in this readme](../b-multi-containers-no-network/readme.md) to setup permissions and the password

### 3. SSH from first container to the second container using the docker container name
   Attach to the first container and ssh to the second container `ssh root@second_container` and follow the prompts.  
   
   ![Establishing ssh connectivity](./_assets/02-ssh-from-container-to-container.png)  
   
   Note: Because we have setup the two containers within a docker network we can use docker's service discovery feature to find containers by name rather than having to find their IP-Addresses.
   
   
   
   *Illustrative trace of the setup*  
   ![multiple-instances](./_assets/01-start-multiple-instances.png)   

### [Back](../readme.md)
