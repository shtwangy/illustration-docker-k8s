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



## Ship

## Run
