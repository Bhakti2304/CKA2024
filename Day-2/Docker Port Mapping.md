## Docker Port Mapping

- Port mapping in Docker is the process of mapping a port on the host machine to a port in the container.
- This is essential for accessing applications running inside containers from outside the Docker host.

- Imagine if your Web app. running inside a Docker container on a Port 3200. By default, this port is accessible within a Docker network only and not from your host machine or external network.
- To make this server accessible outside the container, you need to forward a port from host to cotainer.

  docker run -p <host_port>:<container_port> <image_name>

  -p shows port mapping
