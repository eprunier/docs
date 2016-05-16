<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [Create a container](#create-a-container)
- [Detach and attach to a running container](#detach-and-attach-to-a-running-container)
- [Find and delete dangling volumes](#find-and-delete-dangling-volumes)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## Create a container

Create a container from a CentOS 7 image and run a Bash shell

    $ docker run -it centos:7 /bin/bash

Options:
* -i : interactive mode, keep STDIN open
* -t : associate a pseudo TTY

## Detach and attach to a running container

Detach from a running container : CTRL+p+q

Attach to a running container:

    $ docker attach <container-id>

## Find and delete dangling volumes

Find volumes :

    $ docker volume ls -f dangling=true

Delete volumes : 

    $ docker volume rm $(docker volume ls -f dangling=true)
