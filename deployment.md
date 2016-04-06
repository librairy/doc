# Deployment

In order to facilitate the installation of *librairy*, all the services are packaged as Docker-Images and uploaded to [Docker-Hub](https://hub.docker.com/u/librairy/dashboard/) and uploaded to [Docker-Hub](https://hub.docker.com/u/librairy/dashboard/).

The only prerequisite to consider is to have installed [Docker-Compose v2](https://docs.docker.com/compose/) in your system.

## Get Started!

*librairy* is a composition of services, so you can combine them freely. This means that you can create a unique `docker-compose.yml` descriptor including all the services or as `docker-compose.yml` descriptors as services you need. 

In any case, first of all you need to deploy the [base](https://github.com/librairy/base) service which contains the storage       systems and the message broker required to communicate services.

>*It is recommended to create a root folder named `/librairy` and then a folder hierarchy based on services. In such way, each service descriptor (`docker-compose.yml`) is organized by service*.


Create a folder named `base/` and put inside the file `docker-compose.yml` with the following text:
```yml
version: "2"
services:
 column-db:
   container_name: column-db
   image: librairy/column-db:1.0
   restart: always
   expose:
     - "9042"
     - "9160"
   ports:
     - "5010:8080"
     - "5011:9042"
     - "5012:9160"
   networks:
     - "db"
 document-db:
   container_name: document-db
   image: librairy/document-db:1.0
   restart: always
   expose:
     - "9200"
     - "9300"
   ports:
     - "5020:9200"
     - "5021:9300"
   networks:
     - "db"
 graph-db:
   container_name: graph-db
   image: librairy/graph-db:1.0
   restart: always
   expose:
     - "7474"
   ports:
     - "5030:7474"
   networks:
     - "db"
 event-bus:
   container_name: event-bus
   image: librairy/event-bus:1.0
   restart: always
   expose:
     - "15672"
     - "5672"
   ports:
     - "5040:15672"
     - "5041:5672"
   networks:
     - "events"
networks:
 db:
 events:
```
and then, deploy it by typing:

```sh
$ docker-compose up
```

Verify that it works on: http://localhost:5040.

Note that by using Docker from OS X or Windows, the host address is not localhost. See [here](https://docs.docker.com/engine/installation) for more details.


### Explorer

[Explorer](https://github.com/librairy/explorer) provides programmatic access to functionality and content of *librairy*. Different facades are offered based on the type of the operation:
* **Management**: Create/Read/Update/Delete (CRUD) resources.
* **Read**: Get a resource by key, e.g. by uri.
* **Search**: Get a sorted list of resources based on internal criterias, i.e. based only on the content of the resource. For example, resources containing the word graphic in their title.
* **Exploration**: Find a path or get resources from their relationships.

Each of them is presented as a RESTful-API using JSON as the return format.

As before, create a folder named `explorer/` and put inside the file `docker-compose.yml` with the following text:
```yml
version: "2"
services:
 explorer:
   container_name: explorer
   image: librairy/explorer:latest
   expose:
     - "8080"
   ports:
     - "8080:8080"
   external_links:
     - column-db
     - document-db
     - graph-db
     - event-bus
   networks:
     - "db"
     - "events"
networks:
  db:
    external:
      name: base_db
  events:
    external:
      name: base_events
```

and then, deploy it by typing:

```sh
$ docker-compose up
```

That's all!! **librairy explorer** should be run in your system now.

Verify that it works on: http://localhost:8080/api.