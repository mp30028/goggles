## Run multiple containers but with permissions and password steps automated


### 1. Start up the containers
  
  `docker compose -f .\multi-containers-automated.yml up -d`  
  
  To stop the instance started with docker-compose run `docker compose -f .\multi-containers-automated.yml down`
  
### 2. Setup permission and password for the root login
  The manual steps to configure root access and change of password after the containers have started are replaced by configuring docker compose to do it.  
  
  **i.** Enabling root access.  
  In the [folder ssh_configs](./ssh_configs) the file ***root_perimission.conf*** has the entry ***PermitRootLogin yes***. This file is mapped in docker compose to `/etc/ssh/sshd_config.d/root_permission.conf` for the second_container and ssh automatically includes it in it's configuration.  
  
  **ii** Resetting the root password.  
  The root passwords are saved in an ***.env*** file and mapped to environment variables which are referenced in the docker compose file.  
  Note: ***.env*** file is ignored by Git and so is not saved to the repository. However a ***sample.env*** file is provided which should be copied, the passwords changed and saved as an ***.env*** file.  
  
  **iii** Start up the containers and wait for them to initialise by watching logs  
  Open a new command window and run `docker logs -f first_container` 
  Open another command window and run `docker logs -f second_container` 
  
  When the initialisation completes you should see something like the illustration below  
  ![Initialisation Logs](./_assets/01-initialisation-logs.png)  
  

### 3. SSH from first container to the second container using the docker container name
   Once the initialisation is complete (see step 2. item iii above) attach to the first container and ssh to the second container `ssh root@second_container` and follow the prompts.  

### [Back](../readme.md)
   
   
  