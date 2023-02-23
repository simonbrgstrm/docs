
---
title: "docker cli"
linkTitle: "docker cli"
date: 2017-01-05
description: >
  docker cli commands.
---

{{% pageinfo %}}
Official documentation.

https://docs.docker.com/engine/reference/commandline/cli/
{{% /pageinfo %}}


### Defaults

List running containers
```console
docker ps 
```

List all docker containers (running and stopped)
```console
docker ps -a
```

Start a container from an image, with a custom name
```console
docker run --name <container_name> <image>
```

Run a container in the background
```console
docker run -d <image>
```


Run a container and expose port
```console
docker run -p 8080:8080 <image>
```

Run a container and remove it when stopped
```console
docker run --rm <image>
```

Run a container and pass in environment variables
```console
docker run --env VAR=myvar <image>
```

Mariadb example
```console
docker run -d --rm -p 3306:3306 --name mariadb --env MYSQL_ROOT_PASSWORD=password mariadb:latest
```

Start or stop an existing container
```console
docker <start|stop> <container_name>
```

Remove a stopped container
```console
docker rm <container_name>
```

Remove all stopped containers
```console
docker container prune
```

Fetch and follow the logs of a container
```console
docker logs -f <container_name>
```

Pull an image from a docker registry
```console
docker pull <image>
```

Open a console inside of an already running container
```console
docker exec -it <container_name> bash/sh
```

### Images

Build an Image from a Dockerfile
```console
docker build -t <image> .
```

Build an Image from a Dockerfile without the cache
```console
docker build -t <image> . –no-cache
```

List local images
```console
docker image ls
```

Delete an Image
```console
docker image rm <image>
```

Remove all unused images
```console
docker image prune
```

### Volumes

Create volume
```console
docker volume create <name>
```

Remove volume
```console
docker volume rm <volume>
```

List volumes
```console
docker volume ls
```

Inspect volume
```console
docker volume inspect <volume>
```


