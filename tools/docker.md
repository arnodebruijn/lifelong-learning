Docker
======


Docker Swarm
------------
Clustering and scheduling tool for docker containers
A swarm consists of 1 or more nodes

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

Dockerfile            defines what goes on in the environment of your container and access to virtualised resources.

docker-compose.yml    describes how docker containers should behave in production.

registry              a collection of docker repositories.
repository            a collection of docker images.


Development cycle
-----------------
Dockerfile
- build
image
- run
container


Architecture
============
Docker host
Docker engine


Useful Commands
===============
Run bash in a new container
  docker run -it IMAGE_NAME bash
  docker run --entrypoint "/bin/bash" -it IMAGE_NAME
Attach to (the same) running container (shows output of entrypoint)
  docker attach CONTAINER_NAME
Run a (second) command in a running container
  docker exec -it CONTAINER_NAME bash
Create new Django project from docker
  docker run -it --rm --user "$(id -u):$(id -g)" -v "$PWD":/usr/src/app -w /usr/src/app django django-admin.py startproject hello_world_django


Pro
===
- Reproducible environments
- Versioned environments
- Portability: many deployment targets (AKS, EKS, Google Kubernetes Engine, IBM Cloud Kubernetes) 
- Isolation between containers
  - Isolate development dependencies between projects
- Isolation between host and application
  - Run your app on any docker host (host-machine agnostic)
- Quickly set up development environment
- Separation of concerns: encourages developers to split monoliths in separate services 
- Functional decomposition: break down a large complex application into smaller, simpler parts
- Popular, lots of support, mind-share
- (Horizontal) scalability 
- Orchestration with tools like Kubernetes and docker-swarm 


Con
===
- Performance hit (in comparison to bare-metal but less than virtualization) 
- Relatively young project 
- Added complexity
  - developing/testing a distributed system
  - implementing inter-process communication
  - handling partial failures
- Learning curve 
- Converting existing monoliths to containers is an upfront cost
- Have to take care in designing stateless containers
- Apps should be able to get terminated at any time
- Any number of containers should be able to run at the same time and not communicate with each other


Must be able to explain
=======================
- difference between ENTRYPOINT and CMD
- difference between volumes and mount
- difference between image and container
- how to persist data
- docker-compose, docker-machine, docker swarm, Kubernetes
- how to make containers aware of each other in a network
- why is it ok that most docker containers run as root inside

- where to pass docker run environment variables
- docker image default dev or prod
- docker-machine start a docker-compose

Tweaks
======
- Cache your virtualenv in a volume so you don't need to reinstall everything on build


Orchestrator
============

Docker Swarm
------------
A swarm consists of multiple Docker Engines

Kubernetes
----------

Docker Host
===========
In order to run docker containers in production we need to provision our servers or install a dedicated OS to function as a Docker host.
We're considering the following turn-key on-premise solutions.


OpenStack
---------
Manage a LARGE pool of compute, storage and networking throughout a data center.

Openshift Container Platform
----------------------------
Enterprise pricing, deliberately vague

Rancher
-------
Rancher Labs Support pricing is based on the number of Rancher management server clusters as well as the number of hosts running Rancher or RancherOS.
- light weight
- open source (Apache 2.0 license)

Docker Enterprise
-----------------
$750 yearly
Not entirely sure what the upside is over the Community Edition

Debian 8
--------
- DIY install docker, docker-machine, docker-compose
- Docker CE 18.06 is the last  supported version
- Doesn't support overlay2, to get docker-machine working need to change to aufs

Debian 9
--------
- DIY install docker, docker-machine, docker-compose (add to ansible script)
