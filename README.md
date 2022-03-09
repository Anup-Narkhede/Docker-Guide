
# Docker Basics

**Docker**

https://docs.docker.com/engine/install/

```js
## help message for docker
docker help

## help message for docker command
docker <sub-command> --help
```

Basic Concepts


![App Screenshot](https://github.com/Anup-Narkhede/Docker-Guide/blob/main/Image1_push-pull_run-commit.png)

**Image**

Images are template that we can use to run for different tasks.
Docker.io supplies us many base images.

Related Commands
```js
## display all images in current docker
docker images

## run as images
docker run <image id/name> <command>

## delete an image
docker rmi <image id/name>

## shortcut for run a temporary image to debug.
docker run --rm -it <image id/name> /bin/bash
docker run --rm -it <image id/name> /bin/sh    # for images without bash
```

**Container**

Container is a running task on docker. It uses an image as template.
We can save changes maked on containers as a new image.

Related commands
```js
## display all running containers
docker ps

## display all containers (including stopped)
docker ps -a

## start a stopped container
docker stop <container id/name>

## execute command in a container
docker exec <container id/name> <command>

## shortcut to go into the container
docker exec -it <container id/name> /bin/bash
docker exec -it <container id/name> /bin/sh    # for container without /bin/bash 

## commit a container as an image
docker commit <container id/name> <image name>[:<tag>]
```
 
**Registry**

Therea are many bas images supplied by docker.io like ubuntu, centos and so on.
And we can set up a registry of ourselves.

Related commands
```js
## get image from registry
docker pull <image name>

## push image to registry
docker push <image name>
```

**Dockerfile**

Docker can build images automatically by reading the instructions from a **Dockerfile**. A Dockerfile is a *text document* that contains all the commands a user could call on the command line to assemble an *image*. Using **docker build** users can create an automated build that executes several command-line instructions in succession.

**Dockerfile Components:**

| Command | Description |
|---------|-------------|
|`FROM`| for base image, this command must be on the top of the dockerfile|
|`RUN`| to execute commands, it will create a layer in image|
|`MAINTAINER`|author/owner/description|
|`COPY`|copy files from local system(docker vm) we need to provide source, destination(we can't download file from internet and any remote repo.) |
|`ADD`|similar to copy but it provides a feature to download files from internet, also extract file at docker image side.|
|`EXPOSE`|to expose ports sucha as port 8080 for tomcat, port 80 for nginx etc.|
|`CMD`|execute commands but during container creation|
|`ENTRYPOINT`|similar to `CMD` but has higher priority over `CMD` , first ccommand will be executed by `ENTRYPOINT` only|
|`ENV`|environment variables|
|`WORKDIR`|The `WORKDIR` command is used to define the working directory of a Docker container at any given time.|
||Any RUN, CMD, ADD, COPY, or ENTRYPOINT command will be executed in the specified working directory. e.g. `WORKDIR /directory`|

**Steps:**

*Dockefile --> Instructions --> Build --> Run*


1. Create a file named Dockerfile.
2. Add instructions in Dockerfile.
3. Build dockerfile to create image.
4. Run image to create container.

