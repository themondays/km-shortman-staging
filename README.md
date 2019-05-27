# Sandbox for Shortman API and Client

This is a sandbox for shortman shortener.

## Requirements

* docker
* docker-compose

## Getting started

To start container, make sure that submodules km-shortman and km-shortman-client available and contain Dockerfile. `git submodule update --init --recursive` will initialise and fetch submodules.
(km-shortman will contain Dockerfile and Dockerfile.dev which is represented for development purpose).

You should start with `docker-compose up -d` which will build `api` and `client` with `postgres` dependency. Please note, `client` container is depending on `api`.

### Up containers

```docker-compose up -d```

### Manage container states

```
docker-compose ps
```
You may also run `start`, `stop`, `restart`

### API Test
#### Create new shortlink
```
curl --request POST \
  --url http://127.0.0.1:4001/api/1.0/links \
  --header 'content-type: application/json' \
  --data '{"link": {
  "url": "https://google.com/"
}}'
```

#### Test redirect
```
curl http://127.0.0.1:4001/api/1.0/links/<hashid>
```

### Troubleshooting

* Phoenix getting rejection error on postgres connect to `localhost`. Make sure that you've mapped correct port.
* Phoenix getting rejection error on postgres connect to `postgres` host. Simply try to restart container, on first run issue may appear because of postgres response delay.

