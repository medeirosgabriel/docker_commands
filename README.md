## **Docker Commands - Study**

## **Images**
- #### sudo docker build -t <IMAGE_NAME> . - Must be in the Dockerfile directory
- #### sudo docker run -it <IMAGE_NAME> - Uploads a container from the passed image
- #### sudo docker rmi $(sudo docker images -q) - Deletes all images

## **Containers**

- #### sudo docker container run -p 8080:80 nginx - Runs container on port 8080

- #### sudo docker container run -d -p 8080:80 <IMAGE> - Run container in the background (does not lose the terminal)

- #### sudo docker container ls - Containers running

- #### sudo docker container ls -a - All containers

- #### sudo docker container stop <CONTAINER_ID> - Stops the container

- #### sudo docker container rm -f $(sudo docker container ls -a -q) - Removes all containers that are not running

- #### sudo docker container run -d -P <IMAGE> - Run container in the background on the port (does not lose the terminal) on a random port

- #### sudo docker container run -d -p 80:80 --name <CONTAINER_NAME> <HOST>

- #### sudo docker container logs <CONTAINER_NAME> - Show the last log

- #### sudo docker container logs -f <CONTAINER_NAME> - Monitor logs in the terminal

- #### sudo docker container top <CONTAINER_NAME> - Processes that a container is running

- #### sudo docker container stats -> Resource status of a container

- #### sudo docker container stats <CONTAINER_NAME>

- #### sudo docker container inspect <CONTAINER_NAME> - Information about the container

- #### sudo docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <CONTAINER_ID> - IP address

## **Networks**

- #### **Types of Networks:**
     - #### **Bridge Network:**
         - #### Standard network between containers
         - #### Internal communication between containers.
         - #### One for each application.
         - #### Example: Front and Back

     - #### **Host Network:** This network aims to deliver all existing interfaces on the docker host to the container

     - #### **Network None:** No external access or access from other containers

- #### sudo docker network ls - Lists created networks

- #### sudo docker container run --name <CONTAINER_NAME> -d --network <NETWORK_NAME> <IMAGE>

- #### sudo docker network inspect <NETWORK_NAME> - Network information

- #### sudo docker container exec -it <CONTAINER_NAME> sh - Runs the container terminal

- #### sudo docker network create <NETWORK_NAME> - Creates a network

- #### sudo docker network create <NETWORK_NAME> --subnet 192.168.134.0/24 --gateway 192.168.134.1 - Creates a network with subnet and gateway

- #### sudo docker network rm <NETWORK_NAME> - Removes a network

- #### sudo docker network prune - Removes networks that are not being used
