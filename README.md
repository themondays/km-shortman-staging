# Sandbox for Shortman API and Client

This is a sandbox for shortman shortener.

## Requirements

* docker
* docker-compose

## Getting started

To start container, make sure that modules km-shortman and km-shortman-client contain Dockerfile
(km-shortman will contain Dockerfile and Dockerfile.dev which is represented for development purpose).

You should start with `docker-compose up -d` which will build `api` and `client` with `postgres` dependency. Please note, `client` container is depending on `api`.

### Up containers

```docker-compose up -d```

### Manage container states

```
docker-compose ps
```
You may also run `start`, `stop`, `restart`

