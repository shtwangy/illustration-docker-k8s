# Docker

## Build
create context directory and shell script
```
$ mkdir myimage
$ cat << EOF > ./myimage/hello.sh
> #!/bin/bash
> echo "Hello, World!"
> exec sleep infinity
> EOF
$ chmod +x hello.sh
```

create docker file
```
$ cat <<EOF > Dockerfile
> FROM ubuntu:20.04
> COPY ./hello.sh /hello.sh
> ENTRYPOINT ["/hello.sh"]
> EOF
```

build container image
```
$ docker build -t myimage:v1 ./myimage
$ docker image ls myimage:v1
```
run container
```
$ docker run --name mycontainer myimage:v1
```
looking into container
```
$ docker exec -it mycontainer /bin/bash
```
stop container
```
$ docker stop mycontainer
```
remove container
```
$ docker rm mycontainer
```

### Register with Docker Hub
rename image
```
$ docker tag myimage:v1 shtwangy/myimage:v1
$ docker image ls shtwangy/myimage:v1
```
push image to Docker Hub
```
$ docker login
$ docker push shtwangy/myimage:v1
```

pull image
```
$ docker pull shtwangy/myimage:v1
```

## Ship

## Run
