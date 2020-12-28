# Jenkins with Docker

A modified version of the [jenkins:lts](https://hub.docker.com/r/jenkins/jenkins) docker image with docker installed in it. Used to run a jenkins instance that can perform docker builds out of the box.

Docker image available at: https://hub.docker.com/r/ims94/jenkins

## Prerequisites

- The host machine should have docker installed as this container requires to mount the `docker.sock` of the host machine as a mounted volume.

## Run
With docker CLI:
```
docker run \
    --publish 8000:8080 \
    --publish 50000:50000 \
    --volume jenkins_home:/var/jenkins_home \
    --volume /var/run/docker.sock:/var/run/docker.sock \
    --name jenkins -d ims94/jenkins:latest
```

With docker-compose (use the `docker-compose.yml` file in the repository):
```
docker-compose up -d
```
