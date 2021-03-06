# FiveM Server Container

[FiveM](https://fivem.net/) server running on [Alpine Linux](https://hub.docker.com/_/alpine/).

## Configuration

See [example directory](https://docs.fivem.net/server-manual/setting-up-a-server/#a-name-servercfgexample-a-server-cfg) for sample config file (`server.cfg`).

## Quickstart

```yml
fivem:
  image: petchstudio/fivem

  stdin_open: true
  tty: true

  volumes:
    # You must provide a server config file
    - ./server.cfg:/srv/server.cfg

    # You must clone from https://github.com/citizenfx/cfx-server-data
    - ./cfx-server-data/resources:/srv/resources
    - ./cfx-server-data/cache:/srv/cache

  ports:
    - "30120:30120/tcp"
    - "30120:30120/udp"
```
