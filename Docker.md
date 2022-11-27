# Docker
- Docker is an open source centralized platform designed to create, deploy and run applications (containerization).
- Docker uses container on the host machine.
- Docker is written in 'go' language.
- Docker consists of an Dockerfile, Docker-images, Docker-container and Docker-hub.
- Docker engine runs natively on linux distros.
- It is a tool that perform OS level virtualization that is containerization.
- Need of docker:
    - Before docker, many users faces the problem that a particular code is running in the developer's system but not on the user's system.
- It's a platform as a service.


# Disadvantages of Docker- 
- Not good for gui application
- Docker is suitable when the development OS and testing OS are same.

# Architecture of Docker
- First create a Dockerfile from which we create an Docker-Image.
- Then we can run the docker image in the docker-container.
- Container has layered file system(it install files in layers).

# Docker is an ecosystem
- Docker Client
    - Users can interact with docker daemon with Docker client.
    - Docker client uses CLI or REST API's to communicate with docker daemon.

- Docker Daemon/Server/engine
    - Docker daemon runs on host OS.
    - It is responsible for running docker containers.

- Docker hub
    - It is similar to github but here it stores docker images in the cloud.
    - There are two types of two registry in docker (Public and Private).

- Docker images
    - Docker images are __read only__ binary template use to create docker-containers.
    - Single file with all the dependencies and configuration to run a program.
    - Ways to create an image
        - Take image from docker hub.
        - Create image from dockerfile.
        - Create image from existing container.

- Docker container
    - Containers are instance of an image just like objects are instance of a class. Image is an template and container is the copy of that template.
    - Container runs the entire applications.

# Basic commands of Docker
- To see all images present in your local machine
```
    - docker images
```
- To find out images in docker hub
```
    - docker search [name of the file]
```
- To download image from docker-hub to local machine
```
    - docker pull [name of the file]
```
- To download and run container( run a container or download and run a container )
```
    - docker run -it --name [name_of_the_container ]  [name of the file]  /bin/bash
     i -> interactive mode 
     t -> terminal
```
- To check servie is start or not
```
    - systemctl status docker
```
- To start a container(only if container is already created)
```
    - docker start [name of container_file]
```
- To go inside the container 
```
    - docker attach [name of container_file]
```
- To see all container
```
    - docker ps -a
```
- To see only running containers
```
    - docker ps
```
- To stop a container
```
    - docker stop [name of the container]
```
- To delete a container
```
    - docker rm [name of the container]
```
- To delete a docker image
```
    - docker image rm [image id]
```
- To stop all running containers
```
    - docker stop $(docker ps -a -q)
```
- Delete all stopped containers
```
    docker rm $ (docker ps -a -q)
```
- Delete all images 
```
    docker rmi -f $(docker images -q)
```
# How to create a docker image via docker container?
- It is useful in that situation when we want to change something in our docker image but we cant as these are immutable.
- The only option we have to create a container via image, make our changes in the container and then make an image out of the container using docker commit command (docker commit [old container name ] [new image name] )

# Dockerfile
- It is basically a text file. It contains some set of instructions.
    ## Dockerfile Components
    ```Dockerfile
    - FROM: THis command must be on top of the dockerfile
    - RUN: To execute commands, it will create a layer in image
    - MAINTAINER: Author/Owner/Description
    - COPY:
    ```

# Docker Volume
- Docker volume is simply a directory inside our container.

- Firstly, we have to declare directory as a volume and then we can share volume with different containers.

- Even if we stop container, still we can access volume.
- Volume will be created in one container and can be access by multiple containers.

- You can declare a directory as a volume only while creating a container.

- You can't create volume from a container.

- Volume will not be included when you update an image.

- You can map volume in two ways:-
    - container <---> container
    - Host <---> container

- __Creating volume from Dockerfile__
    - Create a Dockerfile
    ```Dockerfile
        FROM ubuntu
        VOLUME [ "/myvolume"]
    ```
    - Create an image from the dockerfile[
    ```Dockerfile
    docker build -t myimage .
    ```
    - Now create a container from the image and run.
    - Now we can share volume with other container.

    - Creating a new container
    ```Dockerfile
    docker run -it --name container2 --privileged=true --volumes-from container1 ubuntu /bin/bash
    ```
    
- __Creating volume directly on creating the container.__
    ```Dockerfile
    docker run -it --name container3(new_container_name) -v /volume(directory)  ubuntu(image_name) /bin/bash
    ```
    - Now make some changes in volume directory.
    - Now share one more container and share volume.
    ```Dockerfile
    docker run -it --name container4 --privileged=true --volumes-from container3 ubuntu /bin/bash
    ```
- __Sharing volume from host to container.__
- Select the folder in the host machine which you want to make as volume.
- Then run the following command
```Dockerfile
docker run -it --name container_name -v location_of_volume_in_host:location_of_volume_in_container privileged=true ubuntu /bin/bash
```

- __Some commands related to docker volume__
- docker volume ls
- docker volume create <volume_name>
- docker volume rm <volume_name>
- docker volume prune {removes all unused docker files}
- docker volume inspect <volume_name>
- docker container inspect <container_name>

# Docker port mapping
- It is the process of mapping ports of host with the ports of the container.
- The following command is used for mapping ports
```Dockerfile
docker run -td --name <name_of_container> -p [host_port]:[container_port] <image_name>
```
- To check exposed ports of container, use the following command
```Dockerfile
docker port <name_of_container>
```
- To execute the container
```Dockerfile
docker exec -it <name_of_container> /bin/bash
```
- [Difference between attach and execute command](https://stackoverflow.com/questions/30960686/difference-between-docker-attach-and-docker-exec)

- __What is the diff between expose and publish a docker?__
- Basically we have three options-
- Neither specify expose or -p.(cannot access anywhere)
- Only specify expose.(can only access inside the host machine)
- Specify expose and -p.(anywhere in the world)






