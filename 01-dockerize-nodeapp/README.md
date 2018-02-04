# Building the container image

$ docker build -t kubia .

# Listing locally stored images

$ docker images

# Running the container image

$ docker run --name kubia-container -p 8080:8080 -d kubia

# Accessing your app

$ curl localhost:8080
You’ve hit 44d76963e8e1

# Listing running containers

$ docker ps

# Getting additional info about a container

$ docker inspect kubia-container

# Running a shell inside an existing container

$ docker exec -it kubia-container bash

 -i , which makes sure STDIN is kept open. You need this for entering com-
mands into the shell.
 -t , which allocates a pseudo terminal (TTY).

# Exploring the container from within 

ps aux

# Exit the shell

$ exit

# Stopping a container

$ docker stop kubia-container

# Check stop container list

$ docker ps -a

The -a option prints out
all the containers, those running and those that have been stopped.

# Removing a container

$ docker rm kubia-container

This deletes the container. All its contents are removed and it can’t be started again.

# Tagging an image under an additional tag

$ docker tag kubia luksa/kubia

This doesn’t rename the tag; it creates an additional tag for the same image.

# A container image can have multiple tags
# Listing docker images

$ docker images | head

# Pushing the image to docker hub

Before you can push the image to Docker Hub, you need to log in under your user ID
with the docker login command. Once you’re logged in, you can finally push the
yourid/kubia image to Docker Hub like this:

$ docker push yourid/kubia

# Running the image on a different machine

$ docker run -p 8080:8080 -d assadzakir/kubia