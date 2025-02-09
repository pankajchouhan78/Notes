### What is Docker?
Docker ek tool hai jo applications ko containers ke andar chalata hai.  
Docker is a tool that helps you create and run applications in a special environment called a container. A container makes sure your app works the same way everywhere, whether on your computer or a server.

----------

### Why Use Docker?
Some key reasons to use Docker:
-   **Fast** – Starts in seconds, unlike VMs.
-  **Works Anywhere**: Containers can run on any machine, so no worries about compatibility.
-  **No Conflicts**: Each app has its own environment, so they don’t mess with each other.
-   **Easy to Scale** – Add more containers as needed.

----------

### Dockerfile:
A file that tells Docker how to create a container.
### Example:  
```  
FROM node:14
WORKDIR /app
 COPY . .
RUN npm install
 CMD ["node", "app.js"]
```

5.  ### docker-compose.yml:
 A file to manage multiple containers.
    
### Example:  
```
version: '3'
 services:
 web:
 build: .
 ports:
 - "5000:5000"
db:
 image: postgres
 environment:
 POSTGRES_PASSWORD: example
```
---

### What is a Dockerfile and docker-compose.yml?

-  ** Dockerfile**: A Dockerfile is a text document that contains instructions on how to build a Docker image. It defines the operating system, application dependencies, environment variables, and other configurations needed to create a container. Here's a simple example:
```
FROM node:14
WORKDIR /app
COPY . .
RUN npm install
CMD ["node", "app.js"]
```  
This Dockerfile:
-   Starts with the official Node.js image as the base image.
-   Sets /app as the working directory.
-   Copies the current directory’s contents into the container.
-   Installs the application dependencies using npm.
-   Specifies the command to run the application.
    
-   **docker-compose.yml**: docker-compose.yml is a YAML file used to define and run multi-container Docker applications. With Docker Compose, you can specify services (containers), networks, and volumes in a single file. For example: 
```
version: '3'
services:
web:
build: .
ports:
- "5000:5000"
db:
image: postgres
environment:
POSTGRES_PASSWORD: example
```
This file:
-   Defines two services: web (your application) and db (a PostgreSQL database).
-   Specifies that the web service should be built from the current directory and expose port 5000. 
-   Configures the PostgreSQL container with a password.
    

### What is Docker Architecture and How Docker Works?

Docker’s architecture consists of the following components:
1.  Docker Engine: The core component of Docker, responsible for building, running, and managing containers. It consists of:
    -   Docker Daemon (dockerd): The server-side component that manages Docker containers.
    -   Docker CLI (docker): The command-line interface for interacting with Docker.
    -   Docker REST API: Used by the CLI and other tools to communicate with the Docker daemon.
    
3.  Docker Images: A Docker image is a lightweight, standalone, and executable package that includes everything needed to run an application (code, runtime, libraries, environment variables, etc.).
4.  Docker Containers: A container is a running instance of a Docker image. It contains everything needed to run the application but is isolated from other containers and the host system.
5.  Docker Registry: A storage system for Docker images. Docker Hub is the default registry.
6.  Docker Volumes: Used for persisting data created by and used by Docker containers. 
7.  Docker Networks: Provide communication between containers.
    

### What is Docker Image?

A **Docker Image** is a **blueprint** for creating Docker containers. It contains everything needed to run an application—**code, libraries, dependencies, and configurations**.

### What is Docker Container?

A **Docker container** is a **lightweight, portable package** that includes everything needed to run an application—**code, libraries, and dependencies**. It runs **isolated** from other applications but shares the same **OS kernel**, making it **faster and more efficient** than virtual machines.

### What is Docker Hub?

Docker Hub is a cloud-based registry service where you can store and share Docker images. It’s the default registry used by Docker, and you can find both official images (such as databases and application runtimes) and user-contributed images.
Docker Hub allows you to:
-   Share images with others.
-   Push and pull images to and from the registry.
-   Search for and use public images.
    

### What is Docker Compose?
Docker Compose is a tool for defining and running multi-container Docker applications. With Docker Compose, you can use a docker-compose.yml file to define multiple services, networks, and volumes. It simplifies running applications that require several services (e.g., a web application and a database) by managing the setup, networking, and configuration of those services.

### Docker Commands
Here are some commonly used Docker commands:
-   docker build .: Build a Docker image from a Dockerfile.
-   docker run <image>: Create and start a container from an image.
-   docker ps: List running containers.
-   docker stop <container_id>: Stop a running container.
-   docker start <container_id>: Start a stopped container.
-   docker exec -it <container_id> : Open an interactive shell inside a running container.
-   docker pull <image>: Pull an image from Docker Hub.
-   docker push <image>: Push an image to Docker Hub.
-   docker images: List Docker images on the local machine.
-   docker rm <container_id>: Remove a container.
-   docker rmi <image_id>: Remove a Docker image.
    

### Docker Engine

Docker Engine is the core part of the Docker platform. It’s responsible for building, running, and managing containers. It includes:

-   Docker Daemon (dockerd): The server-side part of Docker that manages containers.    
-   Docker CLI: The command-line interface used to interact with the Docker daemon.
-   Docker REST API: An API that allows other tools to communicate with Docker Engine.
    
### What is Docker For AWS?

Docker for AWS is a service provided by Docker that integrates Docker containers with AWS cloud services. It allows you to easily deploy and manage containerized applications on AWS using the Elastic Container Service (ECS) or Elastic Kubernetes Service (EKS).

### Difference Between Docker Containers and Virtual Machines
1.  **Isolation**: Containers share the **host OS kernel**, while VMs have a **full OS** inside each instance.
2.   **Size**: Containers are **lightweight**, but VMs are **heavier** since they include an entire OS.
3.   **Speed**: Containers **start in seconds**, while VMs **take minutes** to boot.
4.   **Resource Usage**: Containers **share system resources efficiently**, whereas VMs **consume more resources** due to separate OS instances.
5.   **Use Case**: Containers are great for **microservices and development**, while VMs are better for **running full OS environments**.


### Correct Steps to Forcefully Delete Docker Images

Let’s break down the process of ensuring that a Docker image is deleted properly, even if it’s in use by containers:

#### 1. Stop and Remove Containers Using the Image

If the image is being used by one or more containers, you will need to stop and remove those containers first.

-   Stop all running containers:
```
docker stop $(docker ps -q)
```
This will stop all containers that are currently running.
-   Remove all containers (running or stopped): 
```
docker rm $(docker ps -a -q)
```
This will remove all containers, ensuring that no container is holding onto the image.

#### 2. Remove the Docker Image Forcefully

Now that there are no containers using the image, you can delete the image forcefully.
```
docker rmi -f <image_name_or_image_id>
```
This will forcefully delete the image, even if it’s still being referenced by any stopped containers.

Example:
```
docker rmi -f my_image:latest
```
This command will remove the image named my_image:latest forcefully.

#### 3. Remove Dangling Images (Images with no tags)

If you're trying to clean up images that are not in use and have no tags (dangling images), you can run the following command:
```
docker rmi -f $(docker images -f "dangling=true" -q)  
```
This will remove all images that are not tagged and are therefore considered "dangling."

#### 4. Force Remove All Images

If you want to remove all Docker images from your system forcefully, you can do this in two steps:

-   First, remove all containers (this will stop and delete them):
```
docker rm -f $(docker ps -a -q)
```
-   Second, remove all images:
```
docker rmi -f $(docker images -q)
```
This will forcefully remove all Docker images and ensure that no containers are holding onto them.

----------

### Troubleshooting

If these steps still don't work, here are some common issues and solutions:

#### 1. Image is being used by a container

If you try to delete an image that is still in use by a container, Docker will prevent its removal. You must stop and remove the container first. Use the following commands:
```
docker ps -a # To see all containers (running and stopped)
docker stop <container_id_or_name>
docker rm <container_id_or_name>
```
#### 2. Check for Dependent Images

Some images are built on top of others. If you try to remove a base image, Docker might prevent this if there are layers or child images depending on it.

To see if an image is a parent image to others, run:
```
docker images --digests
```

#### 3. Force Remove All Unused Images (Clean up Dangling Images)

You can clean up all unused images (including those that are not tagged and are not being used by any containers) by running:
```
docker image prune -a -f
```
This will remove all unused images, whether dangling or otherwise, and free up space.

----------
