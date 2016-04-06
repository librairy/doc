# Deployment

To  facilitate  the  installation  of  the  system,  each of the services has  been  packaged  as  a  [Docker](https://www.docker.com/)  container  and  uploaded  to  [Docker-Hub](https://hub.docker.com/u/librairy/dashboard/). 

## Get Started!

The only prerequisite to consider is to have installed [Docker-Compose v2](https://docs.docker.com/compose/) in your system.

Once it is installed, you can create your own composition of **librairy** by deploying as docker containers as you need. 

### Base

All the *librairy* compositions require a [common-base](https://github.com/librairy/base) which deploys all the storage systems and the message broker used to communicate the rest of services. You need to run it before to run any other service.


First of all, let's create our a file named docker-compose.yml containing the following services: