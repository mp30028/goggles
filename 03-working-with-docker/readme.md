## Working with Docker

### 1. Starting a single docker container
[Start single container](./a-single-container/readme.md). This example illustrates how to start up the containers using direct docker commands as well as using docker compose.

### 2. Starting multiple docker containers in the default network
[Start multiple containers](./b-multi-containers-no-network/readme.md) using docker compose. In this example no network is defined so the containers get started in a default network. Therefore to connect from one container to the other container requires discovering the ip address of the container within the default network we want to connect to.

### 3. Starting containers in a defined network
[Start multiple containers in a docker network](./c-multi-containers-with-network/readme.md). The key advantage of this is that we can use the container name to discover the service rather than the ip address.

### 4. Starting containers and automating the startup steps
[Start with auto setup of permissions and password](./d-multi-containers-automated-setup/readme.md)

### 5. Improving efficiency using custom built images
The previous step runs initialisation steps that updates the base images with a stack of modules needed to run SSH client and server. Because there are two containers these steps run twice. Also we have to inspect the logs to see when both containers are ready. We can improve on this by building an image with the updates and installs baked in. Then this image can be used to start both the containers. Also there is no need to watch the logs to understand when the updates complete as both containers need to have the image built first. This improves the efficiency quite considerably [Start containers with custom image](./e-containers-based-on-built-image/readme.md)
. 
### [Home](../README.md)