Docker
======


Docker Swarm
------------
Clustering and scheduling tool for docker containers

Docker Machine
--------------
Lets you install and manage Docker Engine on virtual hosts

Docker Cloud
------------
Automated builds only from GitHub or BitBucket


Terminology
-----------
Container
Services              the image for a microservice in the context of some larger application. Codified way of running this one image in production.
Stack                 a group of interrelated services that share dependencies, and can be orchestrated together.

Image                 artifact created after building a docker container.
task                  a single container running in a service

Dockerfile            defines what goes on in the environment of your container and access to virtualized resources.

docker-compose.yml    describes how docker containers should behave in production.

registry              a collection of docker repositories.
repository            a collection of docker images.


Developmentcycle
----------------
Dockerfile
- build
image
- run
container


Usefull Commands
================
Run bash in a new container
  docker run -it IMAGE_NAME bash
  docker run --entrypoint "/bin/bash" -it IMAGE_NAME
Attach to (the same) running container (shows output of entrypoint)
  docker attach CONTAINER_NAME
Run a (second) command in a running container
  docker exec -it CONTAINER_NAME bash
Create new django project from docker
  docker run -it --rm --user "$(id -u):$(id -g)" -v "$PWD":/usr/src/app -w /usr/src/app django django-admin.py startproject hello_world_django
