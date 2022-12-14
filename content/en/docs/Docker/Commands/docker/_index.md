
---
title: "docker"
linkTitle: "docker"
date: 2017-01-05
description: >
  docker commands.
---

{{% pageinfo %}}
Official documentation.

https://docs.docker.com/engine/reference/commandline/cli/
{{% /pageinfo %}}


### Defaults

List running containers
```shell
docker ps 
```

List all docker containers (running and stopped)
```shell
docker ps -a
```

Start a container from an image, with a custom name
```shell
docker run --name {{container_name}} {{image}}
```

Run a container in the background
```shell
docker run -d {{image}}
```


Run a container and expose port
```shell
docker run -p 8080:8080 {{image}}
```

Run a container and remove it when stopped
```shell
docker run --rm {{image}}
```

Run a container and pass in environment variables
```shell
docker run --env VAR=myvar {{image}}
```

Mariadb example
```shell
docker run -d --rm -p 3306:3306 --name mariadb --env MYSQL_ROOT_PASSWORD=password mariadb:latest
```

Start or stop an existing container
```shell
docker {{start|stop}} {{container_name}}
```

Remove a stopped container
```shell
docker rm {{container_name}}
```

Remove all stopped containers
```shell
docker container prune
```

Fetch and follow the logs of a container
```shell
docker logs -f {{container_name}}
```

Pull an image from a docker registry
```shell
docker pull {{image}}
```

Open a shell inside of an already running container
```shell
docker exec -it {{container_name}} bash/sh
```

### Images

Build an Image from a Dockerfile
```shell
docker build -t {{image}} .
```

Build an Image from a Dockerfile without the cache
```shell
docker build -t {{image}} . –no-cache
```

List local images
```shell
docker image ls
```

Delete an Image
```shell
docker image rm {{image}}
```

Remove all unused images
```shell
docker image prune
```

### Volumes

Create volume
```shell
docker volume create {{name}}
```

Remove volume
```shell
docker volume rm {{volume}}
```

List volumes
```shell
docker volume ls
```

Inspect volume
```shell
docker volume inspect {{volume}}
```

docker volume inspect: To inspect the volumes.

