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
$ curl http//localhost:8080
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


