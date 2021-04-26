## Table of contents
* [General info](#general-info)
* [Technology](#technology)
* [Setup](#setup)

## General info

The goal of this project is to containerize and define the deployment of a simple web poll application

There are five elements constituting the application:

Poll, a flask Python web application that gathers votes and push them into a Redis queue.

Redis, which holds the votes sent by the Poll application, awaiting for them to be consumed by the Worker.

Worker, a java application which consumes the votes being in the Redis queue, and stores them into a PostgreSQL database

PostgreSQL database, which (persistently) stores the votes stored by the Worker.

Result, a Node.js web application that fetches the votes from the database and displays the result


## Technology
Project is created with:
* docker-compose version 1.25.5

## Setup
To run this project, install docker on your engine and use docker-compose to build the project
Make sure Docker is running by using systemctl on Linux beforehand.
```sh
systemctl start docker
```
```sh
docker-compose up -d --build --remove-orphans
```
