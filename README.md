# docker_commands examples

docker pull erdisayar/flightmare:ubuntu20

##### see running conatiner
docker ps 

### list all conatiner (active + inactive)
docker ps -a

## run image to create a conatiner
docker container run -it --runtime=nvidia -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix:rw --name flightmare_ubuntu20 erdisayar/flightmare:ubuntu20

# Same Image(erdisayar/flightmare:ubuntu20) but different container name(flightmare_ubuntu20_new)
docker container run -it --runtime=nvidia -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix:rw --name flightmare_ubuntu20_new erdisayar/flightmare:ubuntu20

docker start 42281a0917fc
docker stop 42281a0917fc

docker exec -it 42281a0917fc bash

# kill the docker (Do not do it) it will delete all files which is not in the image if you will re-run the docker
docker rm 42281a0917fc
