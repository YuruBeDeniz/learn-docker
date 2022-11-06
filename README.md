## Learn Docker 

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



docker run hello-docker
terminal: Hello Docker!

go ahead and publish this image to docker hub so that anyone can use this image. Then anyone can go to test or production machine and pull and run this image


see also
https://labs.play-with-docker.com/

### Linux commands
##### Some Linux distributions
Ubuntu, Debian, Alpine, Fedora, CentOS

go to hub.docker.com & search for ubuntu

docker pull ubuntu 
or
docker run ubuntu 

docker ps  --> to see list of processes or running containers
docker ps -a  --> a for all, we can see the stopped containers
docker run -it --> to start a container nad interact with it (-it for interactive)
docker run -it ubuntu

### winpty docker run -it ubuntu
root@35865e920d50:/# --> this is a shell prompt 

these commands running in the shell program takes this commands and passes them to the kernel

shell is a program that takes our commands and passes them to the operating system for execution for execution

root (represents the currently logged in user)
35865e920d50 (name of the machine)
/# (/ is the highest directory in the file system)
(# means i have the highest priviledges, as i logged in as the root user) ($ for normal users)
some commands: 
echo hello,
whoami
echo $0 --> to see location of this shell program
history --> to see all the commands used lately
!2 --> the last two commands
apt --> advanced package tool
apt list -->all the packages in this DB

before install a package, always update the package DB
apt update --> to update package database
apt install nano
nano

to clear terminal window: ctrl l
to remove:
apt remove nano

to see the content of a file while in another directory, ex:
ls bin
ls /bin 

cd /root

while in the root directory and to get to my home directory:
cd ~

to rename a directory: move command:
mkdir test
mv test docker
to move it to another directory:
mv hello.txt /etc
to remove files:
rm file1.txt 
or a pattern:
rm file*

to remove directories: 
rm -r docker/ 
(-r stands for recursive)

apt install nano
nano file1.txt
cat --> to concatenate or combine multiple files
cat file1.txt --> see the content of the file
more /etc/adduser.conf
to have less -->
apt install less
less /etc/adduser.conf

standard input represents the keyboard,
standard output represents the screen
redirection:
cat file1.txt > file2.txt   
to combine multiple files:
cat file1.txt file2.txt > combined.txt
echo hello > hello.txt


ctl d , ctrl z, ctrl c --> to exit


 

If you don’t want to lose your shell you can trying stopping the container from another terminal on the same docker host.

Open a new shell and execute

$ docker ps # get the id of the running container
$ docker stop <container> # kill it (gracefully)




     