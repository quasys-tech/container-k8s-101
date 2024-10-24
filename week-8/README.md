


Go build from alpine
------------
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build# cd go-alpine/
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build/go-alpine# docker build -t go-alpine:0.1-alpine3.18 . --no-cache
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build/go-alpine# docker image ls
                REPOSITORY     TAG       IMAGE ID       CREATED              SIZE
                go-alpine      latest    f8425c134883   About a minute ago   232MB
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build/go-alpine# docker run -d -p 8080:8080 go-alpine:0.1-alpine3.18
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build/go-alpine# docker ps
                CONTAINER ID   IMAGE                      COMMAND                  CREATED          STATUS          PORTS                    NAMES
                e27ac3d647b1   go-alpine:0.1-alpine3.18   "/go/bin/app"            2 seconds ago    Up 1 second     0.0.0.0:8080->8080/tcp   suspicious_neumann
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build/go-alpine# curl 127.0.0.1:8080/hello
        {"code":200,"result":"Hello World!"}

Go build from Scratch
------------
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build# cd go-scratch/
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build/go-scratch# docker build -t go-scratch:0.1-scratch . --no-cache
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build/go-scratch# docker image ls
                REPOSITORY     TAG              IMAGE ID       CREATED          SIZE
                go-scratch     0.1-scratch      a055baaefdec   7 seconds ago    7.06MB
                go-alpine      0.1-alpine3.18   f8425c134883   16 minutes ago   232MB
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build/go-scratch# docker run -d -p 8081:8080 go-scratch:0.1-scratch
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build/go-scratch# docker ps
                CONTAINER ID   IMAGE                      COMMAND                  CREATED          STATUS          PORTS                    NAMES
                1f212558d0ae   go-scratch:0.1-scratch     "/go/bin/app"            27 seconds ago   Up 27 seconds   0.0.0.0:8081->8080/tcp   happy_goldwasser
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build/go-scratch# curl 127.0.0.1:8081/hello
        {"code":200,"result":"Hello World!"}

Compare Alpine and Scratch
------------
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build/go-scratch# docker image ls
                REPOSITORY     TAG              IMAGE ID       CREATED          SIZE
                go-scratch     0.1-scratch      a055baaefdec   5 minutes ago    7.06MB
                go-alpine      0.1-alpine3.18   f8425c134883   21 minutes ago   232MB
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build/go-alpine# docker build -t go-alpine:0.1-alpine3.18 . --no-cache
        [+] Building 95.6s (11/11) FINISHED
        ...
        ...
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build/go-scratch# docker build -t go-scratch:0.1-scratch . --no-cache
        [+] Building 69.8s (11/11) FINISHED
        ....
        ....
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build/go-scratch# dive go-scratch:0.1-scratch
        root@container101-ubuntu:~/container-k8s-101/week-1/Docker-Build/go-scratch# dive go-alpine:0.1-alpine3.18

Explore the Container Storage Layers
------------

        dive <image-name>
