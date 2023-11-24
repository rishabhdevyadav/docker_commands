# docker_commands examples

docker ps
docker ps -a

docker container run -it --runtime=nvidia -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix:rw --name flightmare_ubuntu20 erdisayar/flightmare:ubuntu20

docker start 42281a0917fc
docker stop 42281a0917fc

docker exec -it 42281a0917fc bash

## kill the docker (Do not do it) it will delete all files which is not in the image if you will re-run the docker
docker rm 4ad5299f8674ba3b5d3e5437f905c6c2117a478af158d8ab3474f5fed7a3d92b
