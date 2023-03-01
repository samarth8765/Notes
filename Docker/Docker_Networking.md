# Docker Networking
>-There are different methods via which we can communicate to docker containers
>1. Container to WWW communication.
>2. Container to local host communication.
>3. Container to Container communication.

>- We can create a docker network using `docker network create [network_name]`.
>- Then we can use these networks `docker run -p p1:p2 --network [network_name] [image_name].   
>- When in the same network docker itself maps name of the container with the ip of the container.
    