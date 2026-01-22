## Run multiple containers with Docker Compose


### 1. Startup containers with docker compose
  
  `docker compose -f .\multi-containers-no-net.yml up -d`  

  This will start up two ubuntu containers. 
  
  To stop the containers started with docker-compose run `docker compose -f .\multi-containers-no-net.yml down`
  
### 2. Attach and check the running containers
  
  `docker exec -it first_container bash` attach to the first container and run a simple command as a check  
  
  
### 3. Check the SSH service is running  
  `service --status-all` check the status of the services. If the ***ssh*** service is not running we need to start it  
  
  
### 4. Start the SSH service  
  `service ssh start` and check it started with `service --status-all`  
  
### 5. Start SSH Service on the second container
   Exit out of the first_container and attach to the second_container. Check and start the ssh service in this container as done in the first_container.  
  
  
### 6. Permit root login on the second container
   Edit ssh configs using the nano editor `nano /etc/ssh/sshd_config`  
   Find the authentication section and change the line  
   &nbsp;&nbsp;&nbsp;**\#PermitRootLogin prohibit-password**&nbsp;&nbsp;&nbsp; to &nbsp;&nbsp;&nbsp;**PermitRootLogin yes**&nbsp;&nbsp;&nbsp;.  

### 7. Restart the **SSH** service on the second container
   Restart **ssh** service for the changes to effect `service ssh restart`.  

### 8. Change the root password on the second container
   `passwd root`  

### 9. Find the IP-Address of the second container
   Exit out of the second container then get its ip-address and make a note of it `docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' second_container`  
  
### 10. From the first container ssh to the second container  
   Attach to the first container and ssh to the second container `ssh root@<ip_address_from_previous_step>` and follow the prompts.
   
   *Illustrative trace*  
   ![multiple-instances](./_assets/02-start-multiple-instances.png) 

 ### [Back](../readme.md)