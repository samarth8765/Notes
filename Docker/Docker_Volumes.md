# Docker Volumes
>- Volumes are folders on host machine hard drive which are mounted into containers.
>- A volume will link with a container and any changes made on either side will be reflected on both sides.
>- Volumes persists even if the container is shutdowns. 
>- A container can read/write data into the volumes.

>- ## Two type of External Data Storages
>1. Volumes (Managed by Docker)
>2. Bind Mounts (Managed by user)

>- ## Types of volumes
>1. Anonymous volumes 
>- These volumes are deleted as soon as container associated to it is deleted. 
>2. Named volumes 
>- These volumes are not deleted as soon as container associated to it is deleted.
>- __We cant create named volume inside the docker file__. 

>- ## Bind Mounts
>- These are the type of data storage which is controlled by the user and editing of code is possible in container as user knows where the volume is stored.
>- Since it is specific to the container we cannot define this in the dockerfile

