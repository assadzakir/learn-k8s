# Building the container image

$ docker build -t kubia .

# Listing locally stored images

$ docker images

# Running the container image

$ docker run --name kubia-container -p 8080:8080 -d kubia

# ACCESSING YOUR APP

$ curl localhost:8080
You’ve hit 44d76963e8e1

# Listing running containers

$ docker ps

# GETTING ADDITIONAL INFORMATION ABOUT A CONTAINER

$ docker inspect kubia-container

# RUNNING A SHELL INSIDE AN EXISTING CONTAINER

$ docker exec -it kubia-container bash

 -i , which makes sure STDIN is kept open. You need this for entering com-
mands into the shell.
 -t , which allocates a pseudo terminal (TTY).

# EXPLORING THE CONTAINER FROM WITHIN

ps aux

# EXIT THE SHELL

$ exit

# Stopping a container

$ docker stop kubia-container

# CHECK STOP CONTAINER LIST

$ docker ps -a

The -a option prints out
all the containers, those running and those that have been stopped.

# Removing a container

$ docker rm kubia-container

This deletes the container. All its contents are removed and it can’t be started again.

# TAGGING AN IMAGE UNDER AN ADDITIONAL TAG

$ docker tag kubia luksa/kubia

This doesn’t rename the tag; it creates an additional tag for the same image.

# A container image can have multiple tags
# Listing docker images

$ docker images | head

# PUSHING THE IMAGE TO DOCKER HUB

Before you can push the image to Docker Hub, you need to log in under your user ID
with the docker login command. Once you’re logged in, you can finally push the
yourid/kubia image to Docker Hub like this:

$ docker push yourid/kubia

# RUNNING THE IMAGE ON A DIFFERENT MACHINE

$ docker run -p 8080:8080 -d assadzakir/kubia