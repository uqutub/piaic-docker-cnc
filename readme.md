# Docker

#### Build Image

> docker build -t &lt;image-name&gt;:&lt;tag&gt; .
```sh
$ docker build -t myapp:1 .
```

#### Run Container
> docker run --name &lt;container-name&gt; -p &lt;host-port&gt;:&lt;container-port&gt; &lt;image-name&gt;:&lt;tag&gt;
```sh
$ docker run --name cont-name -p 8080:80 myapp:1
```

#### For Test

```sh
$ curl http://localhost:8080
```
#### Cleanup
Running container can be stopped by
```sh
$ docker stop cont-name
```
and removed by
```sh
$ docker rm cont-name
```
With the image it is even simpler. In order to remove it run
```sh
$ docker rmi myapp:1
```
(before removing any Docker image you always must stop all containers that uses the image).

***

### Cheat Sheet

| Command | Description |
| ------ | ------ |
| docker pull user/&lt;image-name&gt;:&lt;tag&gt; | Pulls the image from the docker hub |
| build -t &lt;image-name&gt;:&lt;tag&gt; . | Builds the image from the Dockerfile with the mentioned name and tag |
| docker image ls | Shows the list of the images present on your system. short-hand 'docker images' |
| docker container ls | Displays the only running containers. short-hand 'docker ps'  |
| docker container ls -a | Displays all the containers present on your system. short-hand 'docker ps  -a' |
| docker inspect &lt;image name&gt;:&lt;tag&gt; | Shows the detailed information about the image in JSON format. |
| docker history &lt;image name&gt;:&lt;tag&gt; | Used to inspect the layers of the image. |
| docker tag &lt;source-image&gt;:&lt;tag&gt; &lt;new-image-name&gt;:&lt;tag&gt; | Create a tag of the new image that refers to source image.  |
|docker push user/&lt;image-name&gt;:&lt;tag&gt; | Push an image to a registry |
| docker image rm &lt;image name&gt;:&lt;tag&gt; | Remove the image. short-hand 'docker rmi &lt;image name&gt;:&lt;tag&gt;' |
| docker run --name &lt;container_name&gt; -p &lt;host:port&gt; -d &lt;image_name&gt; | Create the container with the specified name and assign the specified port from the image. |
| docker run --name &lt;container-name&gt; -it -p &lt;host-port&gt; &lt;image-name&gt;:&lt;tag&gt; sh | To run a container from an image in an interactive mode. Press Ctrl + pq it will detach terminal and leave container running in background. |
| docker exec -it &lt;container_name&gt; sh | To go in the running container shell. Write exit to detach the terminal |
| docker stop container_name | It will stop the running container. |
| docker start container_name | Start the stopped container |
| docker rm container_name | Remove the container. |
| docker logs container_name | fetch the logs of the container |
| docker volume create my-vol | Create your Volume for Persistent Data |
| docker volumes ls | List down the volumes |
| docker volume inspect my-vol | inspect the volumes |
| docker volumes rm my-vol | remove volume |
| docker run -d --name mycont -v my-vol:/app nginx:latest | start container with -v flag (volume mount) |
| docker run -d --name devtest --mount source=my-vol,target=/app nginx:latest | start container with --mount flag |
| docker run -d -it --name devtest -v "$(pwd)"/myfolder:/app nginx:latest | start container with bind mounts and -v flag |
| docker run -d -it --name devtest --mount type=bind,source="$(pwd)"/myfolder,target=/app nginx:latest | start container with bind mounts and -mount flag |


