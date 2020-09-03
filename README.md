# docker-tutorial

This is a repo showing the changes I made to the [Getting Started repo](https://github.com/docker/getting-started) while learning about Docker.  

Below are the notes I took while working through the [Docker tutorial](https://github.com/docker/getting-started).

## Docker
### Getting Started

To run this install Docker, clone the repo, and run the command below:

    docker run -d -p 80:80 docker/getting-started

## Guidelines

- Each container should do one thing and do it well. 
- If two containers are on the same network, they can talk to each other. If they aren't, they can't

## Command Cheat Sheet

    docker build -t <container name> <path to docker file>
        
        - Builds a new container image from the specified docker file with a specified name.

    docker run -d -p <host port:container port> <container name>
    
        - Runs a specific image with a specified name and optional flags.

    docker ps
    
        - List the docker processes. 
        - Use this to get the image and container ID for a given container.

    docker exec <container-id> cat /data.txt
    
        - Runs a docker container and immediately executes an arbitrary command(s). 

    docker stop <the-container-id>

        - Stops a currently running container.

    docker rm <the-container-id>

        - Deletes a container.

    docker rm -f <the-container-id>

        - Stops and removes a container in the same command.

    docker login -u YOUR-USER-NAME

        - Logs into Dockerhub

    docker tag <existing image tag> <user id>/<new image tag>

        - Changes an images tag or ID alias.

    docker push <user id>/<image name>
    
        - Pushes a new image to Dockerhub 
    docker network create <image you need networking for>

        - Creates a network interface for a specified image.

    docker exec -it <mysql-container-id> mysql -p

        - Executes a container and immediately prompts mysql for a password.

	docker image history <container-name>

        - Lists the image history for a given container name

    docker run -dp 3000:3000 -v <host volume>:<path/to/named-volume> getting-started
    
        - Connects a volume (-v) from the host to the Docker container.

    docker volume inspect <named volume>
    
        - Reports where the named volume lives on the host.
        - The Mountpoint value is the actual location of the named volume.

## References

- Getting started - https://github.com/docker/getting-started
- Docker official documentation - https://docs.docker.com/reference/
