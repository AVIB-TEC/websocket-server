# websocket-server
[![Docker Image CI](https://github.com/AVIB-TEC/websocket-server/actions/workflows/docker-image.yml/badge.svg)](https://github.com/AVIB-TEC/websocket-server/actions/workflows/docker-image.yml)
[![Node.js CI](https://github.com/AVIB-TEC/websocket-server/actions/workflows/node.js.yml/badge.svg)](https://github.com/AVIB-TEC/websocket-server/actions/workflows/node.js.yml)

This repository contains the code for the Angular webpage visualizations. It is configured with CI/CD on the main branch. 

## Instructions
Created by Pablo Garcia Brenes
Version: 1.0
Date: April 2021

## Running locally
In order to run the webpage locally use the `node ioServer.js` command. This will run the webpage which will be available on `localhost:1617`.


## Modifying CI/CD
In the `.github/workflows` folder you can find the different actions created to make this posible. If you wish to add more branches on which these actions are executed you can add the branch names on the list of branches. For example:

``` yaml
on:
  push:
    branches: [ main ]
  pull_request:
    branches: [ main ]
``` 

On the above code snippet is where you can add the branch names for the action to execute. The `push` and `pull_request` represent the event on which it will execute and for which branches. These don't have to have the same branches. Different ones can be used if desired.



## Create image
`sudo docker build --tag olbapd/avib-server .`

## Create and run container
`sudo docker run  -p 1617:1617  olbapd/avib-server --name avib-server`

If you want to run the container in detach mode then you can run this command.

`sudo docker run -d -p 1617:1617 olbapd/avib-server --name avib-server`

## Updateing Image
Since the repository is configured with CD with docker, once a commit is pushed to remote an action will execute to update the docker image. 