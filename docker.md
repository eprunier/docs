# Docker

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Create an image](#create-an-image)
- [Create a container](#create-a-container)
- [Container attach and detach](#container-attach-and-detach)
- [Clean up](#clean-up)
  - [Container](#container)
  - [Volumes](#volumes)
  - [Images](#images)
- [Docker tools](#docker-tools)
  - [VirtualBox behind a proxy](#virtualbox-behind-a-proxy)
  - [Define disk size when creating VM](#define-disk-size-when-creating-vm)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Create an image

In a directory with a Dockerfile:

    docker build -t <image_name>[:<image_tag>] .

Build behind a proxy :

    docker build -t <image_name>[:<image_tag>] --build-arg http_proxy=<proxy_url> --build-arg https_proxy=<proxy_url> .

## Create a container

Create a container from a CentOS 7 image and run a Bash shell

    docker run -it centos:7 /bin/bash

Options:

- -i : interactive mode, keep STDIN open
- -t : associate a pseudo TTY

## Container attach and detach

Detach from a running container : CTRL+p+q

Attach to a running container:

    docker attach <container-id>

## Network

Docker uses 172.17.0.0 for the docker0 interface.

When creating networks Docker increments the subnet (172.18, 172.19...).
If your local network is on the 172.x.y.z subnet it will may conflict at some point in time with a docker bridge.

To solve this issue you can create a network manually like in the following example

    docker network create --subnet 192.168.1.0/24

Or define the network in your docker-compose file

    networks:
        default:
            driver: bridge
            ipam:
                driver: default
                config:
                    - subnet: 192.168.2.0/24

## Clean up

### Container

Remove dangling containers

    docker container prune

### Volumes

    docker volume prune

or

    docker volume rm $(docker volume ls -f dangling=true -q)

### Images

    docker image prune

or

    docker rmi $(docker images -q -f dangling=true)

## Docker tools

Windows tip for Cygwin shell configuration, put the following code in .zshrc, .bashrc...:

    eval $(docker-machine env default)
    export no_proxy=$no_proxy,$(docker-machine ip default)

### VirtualBox behind a proxy

Create the default VM with the following command:

    docker-machine create -d virtualbox \
    --engine-env HTTP_PROXY=[proxy_url] \
    --engine-env HTTPS_PROXY=[proxy_url] \
    --engine-env NO_PROXY=localhost \
    default

### Define disk size when creating VM

Example for 50GB disk (default value: 20GB)

    docker-machine create -d virtualbox \
    --virtualbox-disk-size 50000 \
    default
