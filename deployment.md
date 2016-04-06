# Deployment

To  facilitate  the  installation  of  the  system,  each of the services has  been  packaged  as  a  [Docker](https://www.docker.com/)  container  and  uploaded  to  [Docker-Hub](https://hub.docker.com/u/librairy/dashboard/). 

## Get Started!

The only prerequisite to consider is to have installed [Docker-Compose v2](https://docs.docker.com/compose/) in your system.

Once it is installed, you can create your own composition of **librairy** by deploying as docker containers as you need.

It is recommended to create a `/librairy` folder as root where the rest of services are located.

### Base

All the *librairy* compositions require a [common-base](https://github.com/librairy/base) which deploys all the storage systems and the message broker used to communicate the rest of services. You need to run it before to run any other service.

Create a `/base` folder and a `docker-compose.yml` file inside it with the following data:

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


### Explorer

It provides programmatic access to functionality and content of *librairy*. Different facades are offered based on the type of the operation:
* **Management**: Create/Read/Update/Delete (CRUD) resources.
* **Read**: Get a resource by key, e.g. by uri.
* **Search**: Get a sorted list of resources based on internal criterias, i.e. based only on the content of the resource. For example, resources containing the word graphic in their title.
* **Exploration**: Find a path or get resources from their relationships.

Each of them is presented as a RESTful-API using JSON as the return format.

Create a `/explorer` folder and a `docker-compose.yml` file inside it with the following data: