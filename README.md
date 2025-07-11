## **Docker Commands - Study**

## **Images**
- #### Build a docker image from a Dockerfile located in the current directory (by default).
  ```sudo docker build -t <IMAGE_NAME> .```
- #### Uploads a container from the passed image
  ```sudo docker run -it <IMAGE_NAME>```
- #### Deletes all images
  ```sudo docker rmi $(sudo docker images -q)```

## **Containers**
- #### Runs container on port 8080
  ```sudo docker container run -p 8080:80 nginx```

- #### Run container in the background (does not lose the terminal)
  ```sudo docker container run -d -p 8080:80 <IMAGE>```

- #### List all running containers
  ```sudo docker container ls```

- #### List all containers
  ```sudo docker container ls -a```

- #### Stops the container
  ```sudo docker container stop <CONTAINER_ID>``` 

- #### Removes all containers that are not running
  ```sudo docker container rm -f $(sudo docker container ls -a -q)```

- #### Run container in the background on the port (does not lose the terminal) on a random port.
  ```sudo docker container run -d -P <IMAGE>```

- #### Create and run a container based on the image <IMAGE_NAME>
  ```sudo docker container run -d -p 80:80 --name <CONTAINER_NAME> <IMAGE_NAME>```

- #### Show the last log
  ```sudo docker container logs <CONTAINER_NAME>```

- #### Monitor logs in the terminal
  ```sudo docker container logs -f <CONTAINER_NAME>```

- #### Processes that a container is running
  ```sudo docker container top <CONTAINER_NAME>```

- #### Resource status of a container
  ```sudo docker container stats```

- #### Monitor in real time the resources used by a specific Docker container
  ```sudo docker container stats <CONTAINER_NAME>```

- #### Information about the container
  ```sudo docker container inspect <CONTAINER_NAME>```

- #### Get the container IP address
  ```sudo docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' <CONTAINER_ID>```

## **Networks**

- #### **Types of Networks:**
     - #### **Bridge Network:**
         - Standard network between containers
         - Internal communication between containers.
         - One for each application.
         - Example: Front and Back

     - #### **Host Network:** This network aims to deliver all existing interfaces on the docker host to the container

     - #### **Network None:** No external access or access from other containers

- #### Lists created networks
  ```sudo docker network ls```

- #### Start a Docker container on a custom network
  ```sudo docker container run --name <CONTAINER_NAME> -d --network <NETWORK_NAME> <IMAGE>```

- #### Network information
  ```sudo docker network inspect <NETWORK_NAME>``` 

- #### Runs the container terminal
  ```sudo docker container exec -it <CONTAINER_NAME> sh```

- #### Creates a network
  ```sudo docker network create <NETWORK_NAME>```

- #### Creates a network with subnet and gateway
  ```sudo docker network create <NETWORK_NAME> --subnet 192.168.134.0/24 --gateway 192.168.134.1```

- #### Removes a network
  ```sudo docker network rm <NETWORK_NAME>```

- #### Removes networks that are not being used
  ```sudo docker network prune```
