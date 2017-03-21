# How to use docker on macOS?

Here is what I learned from the official Docker documentation: Get Started.

## Docker basics

### 1. install "Docker for Mac"

### 2. verify your installation
```
docker version
docker info
docker ps # list running containers
docker run hello-world
docker ps -a # list all containers
```

### 3. run image "whalesay"
```
docker run docker/cowsay cowsay boo
docker ps -a
docker images
```

### 4. build your own image "docker-whale"

#### a. write a Dockerfile
```
mkdir mydockerbuild
cd mydockerbuild

vi Dockerfile
FROM docker/whalesay:latest
# this is important if you are behind a proxy
RUN echo 'Acquire::http::Proxy "http://proxy-addr:proxy-port";' > /etc/apt/apt.conf.d/proxy
RUN apt-get -y update && apt-get install -y fortunes
CMD /usr/games/fortune -a | cowsay
```

#### b. build a image from the Dockerfile
```
docker build -t docker-whale .
```

#### c. run the image
```
docker images
docker run docker-whale
```

### 5. tag, push and pull image

#### a. tag
```
docker images # get the id of the image that you want to tag
docker tag <image-id> feici02/docker-whale:latest
docker images
```
Note: feici02 is my Docker Hub ID.

#### b. push
```
docker login
# push the image to Docker Hub
docker push feici02/docker-whale
```

#### c. pull
```
docker images
docker rmi <images-id> # delete above image
# pull the image from Docker Hub
docker run feici02/docker-whale # it will be downloaded automatically
```

### other useful commands
```
# delete all containers
docker rm $(docker ps -aq)
```
