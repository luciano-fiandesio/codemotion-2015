# Docker demo

## First docker container

	docker search ubuntu

	docker pull ubuntu:latest

	docker images

	docker run ubuntu echo "Hello World"

	docker run -i -t ubuntu bash

## Start a daemonized container

	docker run -d -p 1234:1234 python:2.7 python -m SimpleHTTPServer 1234

	docker ps

	docker-machine ip default

## Start an interactive container

	docker run -i -t ubuntu /bin/bash

	# do stuff in container

	# exit from container using ctrl-p + ctrl+q

	docker ps

	docker attach ###

	exit

	docker ps

## start/stop/rm containers

	docker ps -a

	# restart a container

	docker start ###

	docker ps -a

	# remove a container

	docker rm ###

	# start a daemonized container

	docker run -d -p 1234:1234 python:2.7 python -m SimpleHTTPServer 1234

	# stop it

	docker stop $(docker ps -l -q)

	# remove all stopped containers

	docker rm $(docker ps -a -q)

## images

	docker run -it ubuntu /bin/bash

	apt-get update && apt-get install -y apache2

	exit

	docker ps -l

	docker commit -m "installed apache" <container id> apache2 # apache 2 is the image name

	docker images # Creates a new image from container changes

	docker history apache2

	docker run -ti apache2 bash

	# inside container

	dpkg --get-selections | grep apache

	sudo service apache2 status

## ports and linking

	docker pull wordpress:latest

	docker pull mysql:latest

	docker images

	docker run --name mysqlwp -e MYSQL_ROOT_PASSWORD=wordpressdocker -d mysql

	docker run --name wordpress --link mysqlwp:mysql -p 80:80 -d wordpress

	# link wants source container name : alias name


## volumes

	docker run -ti -v /Users/luciano/Downloads/:/downloads ubuntu /bin/bash

## docker file demo
	
	see demo


## docker compose

	see demo
	








