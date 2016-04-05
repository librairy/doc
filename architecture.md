# Architecture

**librairy** is a system composed by a loosely-coupled set of services connected by an event bus using standardized data protocols and formats. 

![architecture](https://dl.dropboxusercontent.com/u/299257/epnoi/images/epnoi-system.png)

It follows a ***Staged Event-Driven Architecture*** ([SEDA](http://www.eecs.harvard.edu/~mdw/proj/seda/)) that decomposes the flow
into a set of stages connected by queues. When a new element is added to the system, a new event is published trigerring .


