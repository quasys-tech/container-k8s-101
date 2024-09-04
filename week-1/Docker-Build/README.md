Build Commands
------------

        docker build -t custom-nginx .

Create Container
------------

        docker run -d -p 8080:80 custom-nginx

Exec command Inside the Container
------------

        docker exec -it <container_id> hostname

Access Container's Network Namespace
------------

        docker ps
        pid=$(docker inspect -f '{{.State.Pid}}' ${container_id})
        mkdir -p /var/run/netns/
        ln -sfT /proc/$pid/ns/net /var/run/netns/[container_id]
        ip netns exec [container_id] ip a
