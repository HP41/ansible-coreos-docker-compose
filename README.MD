# Ansible Role: coreos-docker-compose
[![Build Status](https://travis-ci.org/HP41/ansible-coreos-docker-compose.svg?branch=master)](https://travis-ci.org/HP41/ansible-coreos-docker-compose)

## This role installs Docker Compose for CoreOS
* Downloads Docker Compose to `/opt/bin` which is a standard location to place binaries as it's writable and in `PATH`.
* Currently downloads Docker Compose v1.14 using URL: `https://github.com/docker/compose/releases/download/1.14.0/docker-compose-Linux-x86_64`.

## Requirements 
* Ansible >= 2.1
* Guest machine: CoreOS

### Default Variables that can be overridden or used as-is when using this role:
* `docker_compose_download_url`: The docker-compose download URL - Default=`https://github.com/docker/compose/releases/download/1.14.0/docker-compose-Linux-x86_64`
* `docker_compose_location`: The location to which docker-compose must be placed. Default=`/opt/bin`, this is a writeable folder and exists within CoreOS's `PATH`
* `docker_compose_filename`: The filename of the docker-compose binary - Default=`docker-compose`
* `docker_compose_location_mode`: The `chmod` mode for the **folder** location where docker-compose will be placed - Default=`0755`
* `docker_compose_file_mode`: The `chmod` mode for the docker-compose **file** - Default=`a+x`