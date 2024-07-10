## Docker Port Mapping

- Port mapping in Docker is the process of mapping a port on the host machine to a port in the container.
- This is essential for accessing applications running inside containers from outside the Docker host.

- Imagine if your Web app. running inside a Docker container on a Port 3200. By default, this port is accessible within a Docker network only and not from your host machine or external network.
- To make this server accessible outside the container, you need to forward a port from host to cotainer.

  ```docker run -p <host_port>:<container_port> <image_name>```

  -p shows port mapping
  
## Docker File

- The Docker file contains a series of instructions to build a Doker image.

- Key instructions in Dockerfile:

  - FROM: Set the base image
  - WORKDIR: Set the working directory
  - COPY: Copies files from the host system to the container
  - RUN: Execute command in container
  - CMD: Specify the command to run once the container starts
  - EXPOSE: Documents which ports the container listens on

## Docker Tags

- Docker tag refers to Docker image.
- It is alias to the ID of Docker image.
- By default, Docker uses the ```latest``` tag.
- Tags can help differentiate between development, staging, and production environments.

```docker tag <source_image>:<tag_name> <target_image>:<tag_name>```  

```docker build -t <user_name>/<image_name>:<tag_name>```

```docker pull <user_name>/<repo_name>:<tag_name>

 
