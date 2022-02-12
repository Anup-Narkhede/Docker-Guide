
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
