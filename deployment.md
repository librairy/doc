# Deployment

In order to facilitate the installation of *librairy*, all the services are packaged as Docker-Images and uploaded to [Docker-Hub](https://hub.docker.com/u/librairy/dashboard/) and uploaded to [Docker-Hub](https://hub.docker.com/u/librairy/dashboard/).

The only prerequisite to consider is to have installed [Docker-Compose v2](https://docs.docker.com/compose/) in your system.

## Get Started!

*librairy* is a composition of services, so you can combine them freely. This means that you can create a unique `docker-compose.yml` descriptor including all the services or as `docker-compose.yml` descriptors as services you need. 

In any case, first of all you need to deploy the [base](https://github.com/librairy/base) service which contains the storage systems and the message broker required to communicate services.

Create a folder named `base/` and put inside the file `docker-compose.yml` containing: 


*It is recommended to create a root folder named `/librairy` and then a folder hierarchy based on services. In such way, each service descriptor (`docker-compose.yml`) is organized by service*.
