# alt:V basic containerized server

This repository contains basic dockerized-containerized alt:V server application packed with js-module, default server data and lightweight MongoDB for simple and adjustable server hosting.

## Requirements:
* Docker
* Docker-compose
* Brain

---

# Running

## Configure
1. Copy default configuration and fit it to your needs:
* `$ cp .env.example .env`
* `$ cp .docker/server.cfg server.cfg`

## Build docker image
`$ docker-compose build`

## Provide server data
* Put your own server resources under **resources** directory.
* If you need to add files under **data** directory, I'd suggest to also download default server data files and mount them via **docker-compose.yml**. Just duplicate last line and provide correct path (inside container it's `/altv/data`).
* The same applies for adding custom modules (container path is `/altv/modules`).

## Start services
`$ docker-compose up -d`

---

# Thanks
* alt:V team for their [free alternative multiplayer client for GTA:V](https://altv.mp).
* Lhoerion for his awesome [alt:V server update script](https://github.com/Lhoerion/altv-serverupdater).
