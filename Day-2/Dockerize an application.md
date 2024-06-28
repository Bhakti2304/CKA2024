# Docker installation and Cheatsheet

docker --version  # Verify Docker Installation
docker info

docker build -t <image_name> . –no-cache  # Build an Image from a Dockerfile without the cache

docker images   # List local images

docker rmi <image_name>     # Delete an Image

docker image prune    # Remove all unused images
