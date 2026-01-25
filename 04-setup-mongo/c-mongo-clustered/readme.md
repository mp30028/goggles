## Approach
This is done by first running a one time docker compose project to :-
1. Change the ownership and permissions of the encryption keys used for securing the MongoDb services
2. Create the MongoDb Replica-Set (i.e. the cluster) and add members to it
3. Create users and enable access controls.

Subsequently we start and stop the cluster with another docker compose project.

## Initialising.
To initialise the run `docker compose -f ./compose-initialise-mongo-cluster.yml up -d`
### Points to note.
  1. The compose project contains four services. The first three services, ***mongo-1*** , ***mongo-2*** and ***mongo-3*** are three nodes that are going to be part of the Replica-Set. 
  2. The fourth service ***init-goggle-rs*** configures the Replica-Set and creates an admin user and roles. 
  3. A file with the ssh-keys on the docker host is mapped to a file in the ***mongo-1*** container. When this container starts it changes the ownership and permissions of this mapped file.

  
## Running the MongoDb cluster
  1. Once initialisation has completed run `docker compose -f ./compose-initialise-mongo-cluster.yml down` to bring down the nodes.
  2. Restart the cluster with `docker compose -f ./compose-mongo-cluster.yml up -d`.
  3. Check the status of the cluster with `docker exec -it mongo-1 mongosh --authenticationDatabase "admin" -u "the_username" -p "the_password" --eval "rs.status()"`. You may have to try this several times or wait for about 30 seconds or so after the restart for the cluster to be up and stablised.
  4. Once the cluster is up run a mongo command to test. Try something like `docker exec -it mongo-1 mongosh --authenticationDatabase "admin" -u "mongo_admin" -p "password" --eval "show databases"`
  
## Generating the ssh keys
Using openssl run `openssl rand -base64 -out example.key 756`  

![Generate Keys](./_assets/03-generate-keys.png)