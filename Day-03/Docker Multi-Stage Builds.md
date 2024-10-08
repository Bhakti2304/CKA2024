# Multi Stage Docker Build

- Multi-stage builds let you reduce the size of your final image, by creating a cleaner separation between the building of your image and the final output. 

## Step 1: Verify Installation

```bash
docker --version
docker info
```

## Step 2: Cloning the Application from GitHub
We will use a sample Node.js application available on GitHub. Clone the repository to your local machine:
```bash
git clone https://github.com/heroku/node-js-sample.git
cd node-js-sample
```
## Step 3: Creating a Dockerfile
A Dockerfile is a text document that contains instructions to build a Docker image.

```bash
touch Dockerfile    # Create Dockerfile
Edit Dockerfile
```
Open the Dockerfile in a text editor and add the following content:

- dockerfile
```yaml
FROM node:14       # Use an official Node.js runtime as the base image

WORKDIR /usr/src/app    # Set the working directory

COPY package*.json ./      # Copy package.json and package-lock.json to the working directory

RUN npm install      # Install dependencies

COPY . .    # Copy the rest of the application code to the working directory

EXPOSE 3000    # Expose the port on which the app runs

CMD ["npm", "start"]    # Command to run the application
```
## Step 4: Building the Docker Image
```bash
docker build -t node-js-sample .      # Build Docker Image
```
**-t node-js-sample: Tags the image with the name "node-js-sample"**
**.: Refers to the current directory where the Dockerfile is located**
```bash
docker images      # Verify Image Creation
```
## Step 5: Running the Docker Container
```bash
Run Docker Container

docker run -d -p 3000:3000 node-js-sample
```
**-d: Runs the container in detached mode**
**-p 3000:3000: Maps port 3000 of the host to port 3000 of the container.**

Access Application
Open a web browser and go to http://localhost:3000 to see the running application.

## Step 6: Benefits of Docker Multistage Build
Multistage builds allow you to use multiple FROM statements in your Dockerfile, which can help **reduce the size of the final image** and improve the build process

- dockerfile

**Stage 1: Build**
```yaml
FROM node:14 as build
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build
```
**Stage 2: Production**
```bash
FROM node:14
WORKDIR /usr/src/app
COPY --from=build /usr/src/app ./
EXPOSE 3000
CMD ["npm", "start"]
```
**Benefits:**

Reduces the size of the final image.
Separates the build environment from the production environment.
Enhances security by only including necessary artifacts in the final image.

## Step 7: Best Practices for Writing a Dockerfile
Best practices:

- Use official images as the base.
- Minimize the number of layers.
- Use multistage builds.
- Leverage .dockerignore to exclude unnecessary files.
- Use specific tags for base images.

## Step 8: Exploring docker init Command
The docker *init*  command helps initialize a new project with Docker support.
```bash
docker init
```
This command will prompt you to set up a Dockerfile and other configuration files for your project.
