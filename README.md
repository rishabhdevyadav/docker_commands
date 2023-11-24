# docker_commands examples

#### download image
```bash
docker pull erdisayar/flightmare:ubuntu20
```

#### see running conatiner
```bash
docker ps 
```

#### list all conatiner (active + inactive)
```bash
docker ps -a
```

#### run image to create a conatiner
```bash
docker container run -it --runtime=nvidia -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix:rw --name flightmare_ubuntu20 erdisayar/flightmare:ubuntu20
```

#### Same Image(erdisayar/flightmare:ubuntu20) but different container name(flightmare_ubuntu20_new)
```bash
docker container run -it --runtime=nvidia -e DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix:rw --name flightmare_ubuntu20_new erdisayar/flightmare:ubuntu20
```

```bash
docker start 42281a0917fc
docker stop 42281a0917fc
exit
```
#### connect to active docker in new shell
```bash
docker exec -it 42281a0917fc bash
```

#### kill the docker (Do not do it) it will delete all files which is not in the image if you will re-run the docker
```bash
docker rm 42281a0917fc
```

### I have container, now i want to build a image from container.
If you have made changes inside a running container and you want to create a new Docker image based on those changes, you can follow these steps:

1. **Identify the Container ID or Name:**
   Use the `docker ps` command to list the running containers and find the Container ID or Name of the container you want to create an image from.

   ```bash
   docker ps
   ```

2. **Commit Changes to a New Image:**
   Use the `docker commit` command to create a new image from the changes made in the container. Replace `container_id` with the actual ID or name of your running container.

   ```bash
   docker commit container_id new_image_name:new_tag
   ```

   For example:

   ```bash
   docker commit my_container my_updated_image:latest
   ```

   This creates a new Docker image with the specified name and tag.

3. **Verify the New Image:**
   You can now use the `docker images` command to verify that the new image has been created.

   ```bash
   docker images
   ```

   Look for the image you just created (`new_image_name:new_tag`).

### Example:

Let's say you have a running container named `my_container`, and you want to create a new image named `my_updated_image:latest`:

```bash
docker commit my_container my_updated_image:latest
```

After running this command, you can then use the new image in subsequent `docker run` commands or push it to a Docker registry if you need to share it with others.

Keep in mind that this approach captures the current state of the container as a new image, but it might not be the most efficient or best practice for all scenarios. In a production environment, consider using Dockerfiles and rebuilding images to ensure reproducibility and maintainability.
