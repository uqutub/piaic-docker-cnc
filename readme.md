# Docker

#### Build Image

> docker build -t <image-name>:<tag> .
```sh
$ docker build -t myapp:1 .
```

#### Run Container
> docker run --name <container-name> -p <host-port>:<container-port> <image-name>:<tag>
```sh
$ docker run --name cont-name -p 8080:80 myapp:1
```

#### For Test

```sh
curl http//localhost:8080
```


