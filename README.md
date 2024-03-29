[![auto-update](https://github.com/digrouz/docker-alpine-s6/actions/workflows/auto-update.yml/badge.svg)](https://github.com/digrouz/docker-alpine-s6/actions/workflows/auto-update.yml)
[![update-alpine](https://github.com/digrouz/docker-alpine-s6/actions/workflows/update-alpine.yml/badge.svg)](https://github.com/digrouz/docker-alpine-s6/actions/workflows/update-alpine.yml)
[![dockerhub](https://github.com/digrouz/docker-alpine-s6/actions/workflows/dockerhub.yml/badge.svg)](https://github.com/digrouz/docker-alpine-s6/actions/workflows/dockerhub.yml)
![Docker Pulls](https://img.shields.io/docker/pulls/digrouz/alpine-s6)

# docker-alpine-s6
Docker base image based on Alpine Line and s6-overlay


## Tag
Several tag are available:
* latest: [Dockerfile_alpine](https://github.com/digrouz/docker-alpine-s6/blob/master/Dockerfile_alpine)

## Description

Small. Simple. Secure. Alpine Linux is a security-oriented, lightweight Linux distribution based on musl libc and busybox.

s6-overlay is an easy-to-install (just extract a tarball or two!) set of scripts and utilities allowing you to use existing Docker images while using s6 as a pid 1 for your container and process supervisor for your services.

https://www.alpinelinux.org/
https://github.com/just-containers/s6-overlay

## Usage
    docker create --name=alpine-s6 \
      -e UID=<UID default:12345> \
      -e GID=<GID default:12345> \
      -e AUTOUPGRADE=<0|1 default:0> \
      -e TZ=<timezone default:Europe/Brussels> \
      digrouz/alpine-s6

## Environment Variables

When you start the `alpine-s6` image, you can adjust the configuration of the `alpine-s6` instance by passing one or more environment variables on the `docker run` command line.

### `UID`

This variable is not mandatory and specifies the user id that will be set to run the application. It has default value `12345`.

### `GID`

This variable is not mandatory and specifies the group id that will be set to run the application. It has default value `12345`.

### `AUTOUPGRADE`

This variable is not mandatory and specifies if the container has to launch software update at startup or not. Valid values are `0` and `1`. It has default value `0`.

### `TZ`

This variable is not mandatory and specifies the timezone to be configured within the container. It has default value `Europe/Brussels`.

## Notes

* This container is built using [s6-overlay](https://github.com/just-containers/s6-overlay)
* The docker entrypoint can upgrade operating system at each startup. To enable this feature, just add `-e AUTOUPGRADE=1` at container creation.

## Issues

If you encounter an issue please open a ticket at [github](https://github.com/digrouz/docker-alpine-s6/issues)
