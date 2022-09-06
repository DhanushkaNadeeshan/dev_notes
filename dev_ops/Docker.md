[Home](../README.md)

[Remove a Volume](#Remove-a-Volume)
[Docker image creating](#docker-image-creating)

#### builder main commands
| Command | Description |
|---------|----------|
| FROM image:scratch | base image for the build |
| MAINTAINER email | name of the mainainer (metadata)|
| COPY path dst | copyt path from the context into the container at location dst|
| ADD src sdt | same as COPY but untar archives and accepts http url|
| RUN args | run an arbitary command inside the container|
| USER name | set the default username|
| WORKDIR path | set the default working directory|
|CMS args | set default command |
|ENV name value | set and environment variable|





#### Docker image creating
`docker build -t yourusername/repository-name .`

#### Reatag the image with a version number
`docker tag <image>  <image>:<version>`

#### list all
`docker images`  or `docker image ls`

#### view logs
`docker logs <container id>`
### start container
`docker start <id>`

#### stop container
`docker stop <container id>`

#### inspect a container
`docker inspect <container id>`

#### run docker image
d - depatch
p - port
`docker run -dp <outport>:<internalport> --name <identify name> <image>`

### remove runnig container
`docker rm -f <id/name>`

#### create  volume
`docker volume create <name>`

#### List volume
`docker volume ls`

####  inscpect volume
`docker volume inspect <name>`

#### Remove a Volume
`docker volume rm <name>`
#### start a container with a volume
````shell
docker run -d \
  --name devtest \
  --mount source=myvol2,target=/app \
  nginx:latest
````

# docker compose

```yml
version: "3.9"
services:
  frontend:
    image: node:lts
    volumes:
      - myapp:/home/node/app
volumes:
  myapp:
    external: true
```





