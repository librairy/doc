# Event Bus
Following a publisher/subscriber approach, all the modules in the system can publish and read  events to notify and to be notified about the system state. 

For example, when a new item is created, an event-message will be published to the channel:  `item.created`. This event will be managed by the learner module to begin to analyze all the  items in that domain and also by the modeler module to begin to build models which represent  these items. Therefore, the system flow is not unique and is not directly implemented, instead  parallel and emergent flows can appear according to particular actions on resources. 

We use the *Advanced Message Queuing Protocol* ([AMQP](http://www.amqp.org/)) as our messaging standard to avoid any  cross-platform problem and any dependency to the selected message broker. This protocol defines  the following elements: `exchange`, `queue` and `routing-key`. 


![event-bus-sample](https://dl.dropboxusercontent.com/u/299257/librairy/figures/event-bus-sample.png)

In this scenario, a *producer* module sends a message to the `exchange` element, instead of a `queue`,  along with a `routing-key`. That `exchange` may be bound to `queues` through *topic* and *group* bindings defined by a module. A *topic binding* is a directive indicating what messages should be routed from an `exchange` to a `queue`. The *group binding* allows system to deliver a message only  to one *consumer* sharing the same *group* value, getting a dynamic distribution of load between them. 

Consumer  modules  listening  to  `queues`  bounded  to  the  `exchange`  by  a  topic  binding  that  match  to the `routing-key` used to sent the message, will receive that message. 

We adopted the *exchange paradigm* for building our event-bus. Thus, every module (i.e. explorer, learner,  modeler, etc) defines the kind of events to listen by the *binding-key* used to bound its queue to the  `exchange`. The messages are sent with a `routing-key` to `queues` using a `binding-key` that matches with  that  `routing-key`.  These  `queues`  are  not  shared  among  different  modules,  but  yes  among  the  instances of the same module when the system is running on a cluster.

Considering  only  systems  that  offer  persistence  and  replication  as  well  as  routing,  delaying  and  redelivering implementing the AMQP protocol, we used the RabbitMQ Message Broker.