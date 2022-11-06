create a file named Dockerfile without any extension

go to Docker Hub (registry for docker images)
hub.docker.com 

e.g. seach for node and check the official node image
check for images

then, make a tag using a column to specify which linux distribution we want to use
FROM node:alpine
(with alpine image will be very small)

to copy all the files in the current directory (use .) into the app directory (use /app) into that image. So that the image has a file system and in that file system we will create a directory called app

to execute a command:
CMD node /app/app.js
(this file is inside the app directory so we add app/)
or, alternatively
WORKDIR /app
CMD node app.js

to package up the app:
go to terminal and command docker to package up the app
-t: to tag the image
.: to specify where docker can find a docker file. (. means we are currently inside hello docker directory (cd hello-docker))
docker build -t hello-docker .

to see all the images in this computer
docker images 
or
docker image ls# learn-docker
