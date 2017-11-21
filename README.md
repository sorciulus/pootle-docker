# Docker - Pootle translation server

## Configuration

In environment.yml file you set Mysql and Pootle credentials before start docker.

## Start

As pootle consists of multiple components, we provide a `docker-compose.yml` to bring up and connect all the services.  
Use the following command to bring up the environment:

    docker-compose up -d

**Notice:** The mysql-server and the redis cache are not accessible by the outside world. Only the pootle container can access those services.

**Notice:** The first time run pootle you will need to configure (migrate, initdb) according to the credentials. This will take time. 

