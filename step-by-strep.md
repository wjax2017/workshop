# Step By Step

## Docker

## Installation

[Install for Mac: https://docs.docker.com/docker-for-mac/install/](https://docs.docker.com/docker-for-mac/install/)
[Install for Ubuntu: https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/](https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/)
[Install for CentOS: https://docs.docker.com/engine/installation/linux/docker-ce/centos/](https://docs.docker.com/engine/installation/linux/docker-ce/centos/)

## Basics

### Docker commands

`docker version`

`docker ps`

`docker images`

`docker run | start | stop | kill`

`docker pull`

`docker push`

## Tasks

## Install mysql

[Docker HUB: https://hub.docker.com/_/wordpress/](https://hub.docker.com/_/mysql/)

`docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -d mysql`

`docker ps`

## Install Wordpress

[Docker HUB Wordpress: https://hub.docker.com/_/wordpress/](https://hub.docker.com/_/wordpress/)

`docker run --name some-wordpress -p 81:80 --link some-mysql:mysql -d wordpress`

`docker ps`

## Open Wordpress

[http://localhost:81](http://localhost:81)

## Configure and play with it

## Stop and restart mysql and wordpress

### Stop

`docker stop some-wordpress`

`docker stop some-mysql`

### Start

`docker start some-mysql`

`docker start some-wordpress`

## Remove mysql and wordpress

`docker kill some-mysql`

`docker kill some-wordpress`

`docker rm some-mysql`

`docker rm some-wordpress`

## Rerun MySQL and Wordpress

Have a look at what happens and think about it.

## Creating Volume mappings

`mkdir -p data/{mysql,wordpress}`

## Starting with mappings

`docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -v $(pwd)/data/mysql:/var/lib/mysql -d mysql`

`docker run --name some-wordpress -p 81:80 --link some-mysql:mysql -v $(pwd)/data/wordpress:/var/www/html -d wordpress`

## Open in Browser

[http://localhost:81](http://localhost:81)

## Destroy and remove containers

`docker kill some-mysql`

`docker kill some-wordpress`

`docker rm some-mysql`

`docker rm some-wordpress`

## Rerun MySQL and Wordpress

`docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=my-secret-pw -v $(pwd)/data/mysql:/var/lib/mysql -d mysql`

`docker run --name some-wordpress -p 81:80 --link some-mysql:mysql -v $(pwd)/data/wordpress:/var/www/html -d wordpress`

## Open in Browser

[http://localhost:81](http://localhost:81)

