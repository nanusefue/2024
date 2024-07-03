docker network create front
docker network create data

docker run --name webfront -it -d --network front debian
docker run --name webback -it -d --network back -d debian

docker network connect front containerID (webback)

docker run --name webdata -it -d --network back -d debian


docker exec -it containerID(webback) bash
webback> ping webfront
webback> ping webdata

docker exec -it containerID(webfront) bash

webfront> ping webback
webfront> ping webdata xxxxx no se puede.

-----

docker network create my-net --subnet 10.10.10.0/29 --ip-range 10.10.10.0/30
docker run -it --rm --name app --network my-net busybox:latest
docker run -it --rm --name app2 busybox:latest
docker network connect my-net app2