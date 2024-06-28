# Docker installation and Cheatsheet

- Docker provides the ability to package and run an application in a loosely isolated environment called a 'container'.

Docker Desktop is available for Mac, Linux and Windows
https://docs.docker.com/desktop

### IMAGES
docker --version          **Verify Docker Installation**
docker info

docker build -t <image_name>       **Build an Image from a Dockerfile**

docker build -t <image_name> . –no-cache        **Build an Image from a Dockerfile without the cache**

docker images         **List local images**

docker rmi <image_name>           **Delete an Image**

docker image prune          **Remove all unused images**

### DOCKER HUB

docker login -u <username>         **Login into Docker**

docker push <username>/<image_name>         **Publish an image to Docker Hub**

docker search <image_name>             **Search Hub for an image**

docker pull <image_name>               **Pull an image from a Docker Hub**

docker -d             **Start the docker daemon**

docker --help          **Get help with Docker**

docker info         **Display system-wide information**

### CONTAINERS

docker run --name <container_name> <image_name>        **Create and run a container from an image, with a custom name**

docker run -p <host_port>:<container_port> <image_name>         **Run a container with and publish a container’s port to the host**

docker run -d <image_name>          **Run a container in the background**

docker start|stop <container_name> (or <container-id>)            **Start or stop an existing container**

docker rm <container_name>          **Remove a stopped container**

docker exec -it <container_name> sh          **Open a shell inside a running container**

docker logs -f <container_name>          **Fetch the logs of a container**

docker inspect <container_name> (or <container_id>)            **To inspect a running container**

docker ps             **To list currently running containers**

docker ps --all            **List all running and stopped docker containers**

docker container stats         **View resource usage stats**
