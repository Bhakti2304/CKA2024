## Download Docker desktop client
```
https://www.docker.com/products/docker-desktop/
```

## Get started
- Clone a sample git repository using the below command or use your project for the demo:

```bash
git clone https://github.com/docker/getting-started-app.git
```

- cd into the directory
```bash
cd getting-started-app/
```
- Create an empty file with the name **Dockerfile**
```bash
touch Dockerfile
```
- Using the text editor of your choice, paste the below content
```yaml
FROM node:18-alpine
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000
```

- Build the **docker image** using the application code and **Dockerfile**

```bash
docker build -t day02-todo .
```
- Verify the image has been created and stored locally using the below command:
```bash
docker images
```

- Create a public repository on hub.docker.com and push the image to remote repo
```bash
docker login
docker tag day02-todo: latest username/new-reponame:tagname
docker images
docker push username/new-reponame:tagname
```

- To pull the image to another environment, you can use the below command
```bash
docker pull username/new-reponame:tagname
```

- To start the docker container, use the below command
```bash
docker run -dp 3000:3000 username/new-reponame:tagname
```

- Verify your app. Your app should be listening on localhost:3000
- To enter(exec) into the container, use the below command
```bash
docker exec -it container_name sh
or
docker exec -it container_id sh
```
  -it flag refers to the interactive mode which allows you to interact with the container's shell

- This can be useful for debugging, running admin tasks, creating folders/volumes, or inspecting the state of the container.

- To view docker logs

```bash
docker logs containername
or
docker logs containerid
```
