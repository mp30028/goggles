## Run multiple containers but with permissions and password steps automated


### 1. Start up the containers
  
  `docker compose -f .\multi-containers-automated.yml up -d`  
  
  To stop the instance started with docker-compose run `docker compose -f .\multi-containers-automated.yml down`
  
### 2. Setup permission and password for the root login
  These steps no longer needed

### 3. SSH from first container to the second container using the docker container name
   Attach to the first container and ssh to the second container `ssh root@second_container` and follow the prompts.  
   
   ![Establishing ssh connectivity](./_assets/01-ssh-from-container-to-container.png)  
   
   
  