# WordPress

This repository contains the setup for a WordPress blog and a MariaDB. Each service runs in its own container.
A WordPress admin user and MariaDB user are created via the environment variables. An [example.env](example.env) is provided.

## Table of contents

1. [Prerequisites](#prerequisites)
1. [Quickstart](#quickstart)
1. [Usage](#usage)
    - [Configuration](#configuration)
    - [Containerization](#containerization)
        - [Access container logs](#access-container-logs)
        - [Start/Stop the application](#startstop-the-application)
        - [Remove the containers](#remove-the-containers)

## Prerequisites

- Docker Engine or Docker Desktop

## Quickstart

In order to quickly get started with the project follow these steps:

1. clone the repository
1. navigate to the repository
1. configure required application environment variables
    1. `cp example.env .env`
    1. edit the .env file
1. build and run the containers
    - `docker compose up -d`
1. (optional) show container logs
    - `docker compose logs -f`
1. verify the application is running by visiting `localhost:8080` (or the port you configured in the .env)

## Usage

### Configuration

1. Create (or copy) the [.env](example.env) file to configure the application.
```sh
cp example.env .env
```
The file has to be in the root directory. Otherwise you need to reference it in the docker compose command.
2. Edit the environment variables. Make sure to use strong passwords if the application is exposed to the internet.

### Containerization

You can build and run the containers with a simple command:
```sh
# use -d to run the containers in the background
# you can use --env-file /path/to/your/.env if it's not in the root directory
docker compose up -d
```
This will build and start both containers. 

#### Access container logs

To see the log files of the application, you can use:
```sh
docker compose logs -f
```
Closing this terminal will not stop the containers.

#### Start/Stop the application

If you want to stop the application (and all containers of it) use:
```sh
docker compose stop
```

To start it again:
```sh
docker compose start
```

#### Remove the containers

You can remove the containers with
```sh
docker compose down
```
if you don't need them anymore.