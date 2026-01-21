## Run multiple containers based on a custom image built with a Dockerfile
Docker can build images automatically by reading the instructions from a Dockerfile. A Dockerfile is a text document that contains all the commands a user could call on the command line to assemble an image. This page describes the commands you can use in a Dockerfile.

Previously we executed the following :-  
**i.** Started containers with a base linux image.  
**ii.** Once the containers start a handful of shell commands run to  update and install the tools and applications needed using a package manager such ***apk*** or ***apt***.
**iii.** In the automated setup docker compose is configured to map and mount a local file to update ssh configuration in the container to permit root level access over ssh.
**iv.** Finally environment variables are configured in an ***.env*** file to hold passwords which can be referenced within docker compose to change the root password within the containers.

It would be more efficient and quicker if the images already contained the updates and the tools.  
Docker can build images with the updates and tools ready installed using a Dockerfile that contains the commands to assemble the image.
