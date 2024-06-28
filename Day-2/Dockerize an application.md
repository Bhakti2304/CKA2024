# Docker installation and Cheatsheet

docker --version          # Verify Docker Installation
docker info

docker build -t <image_name> . –no-cache        # Build an Image from a Dockerfile without the cache

docker images         # List local images

docker rmi <image_name>           # Delete an Image

docker image prune          # Remove all unused images

docker login -u <username>         # Login into Docker

docker push <username>/<image_name>         # Publish an image to Docker Hub

docker search <image_name>           # Search Hub for an image

docker pull <image_name>             # Pull an image from a Docker Hub

docker -d           # Start the docker daemon

docker --help         # Get help with Docker

docker info        # Display system-wide information
