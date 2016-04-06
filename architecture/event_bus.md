# Event Bus
Following a publisher/subscriber approach, all the modules in the system can publish and read  events to notify and to be notified about the system state. 

For example, when a new item is created, an event-message will be published to the channel:  `item.created`. This event will be managed by the learner module to begin to analyze all the  items in that domain and also by the modeler module to begin to build models which represent  these items. Therefore, the system flow is not unique and is not directly implemented, instead  parallel and emergent flows can appear according to particular actions on resources. 

We use the *Advanced Message Queuing Protocol* ([AMQP](http://www.amqp.org/)) as our messaging standard to avoid any  cross-platform problem and any dependency to the selected message broker. This protocol defines  the following elements: `exchange`, `queue` and `routing-key`. 


![event-bus-sample](https://dl.dropboxusercontent.com/u/299257/librairy/figures/event-bus-sample.png)

In this scenario, a *producer* module sends a message to the `exchange` element, instead of a `queue`,  along with a `routing-key`. That `exchange` may be bound to `queues` through *topic* and *group* bindings defined by a module. A *topic binding* is a directive indicating what messages should be routed from an `exchange` to a `queue`. The *group binding* allows system to deliver a message only  to one *consumer* sharing the same *group* value, getting a dynamic distribution of load between them. 

Consumer  modules  listening  to  `queues`  bounded  to  the  `exchange`  by  a  topic  binding  that  match  to the `routing-key` used to sent the message, will receive that message. 

We adopted the *exchange paradigm* for building our event-bus. Thus, every module (i.e. explorer, learner,  modeler, etc) defines the kind of events to listen by the *binding-key* used to bound its queue to the  `exchange`. The messages are sent with a `routing-key` to `queues` using a `binding-key` that matches with  that  `routing-key`.  These  `queues`  are  not  shared  among  different  modules,  but  yes  among  the  instances of the same module when the system is running on a cluster.

Considering  only  systems  that  offer  persistence  and  replication  as  well  as  routing,  delaying  and  redelivering implementing the AMQP protocol, we used the [RabbitMQ Message Broker](http://www.rabbitmq.com/).

## Routing-Key
In general, a `routing-key` can be defined by a list of words delimited by dots. In our case, it consists of only two words separated by one dot:

```
                                    <resource|relation>.<status>
```
The first part identifies the resource associated to the event, and the second one is its current status. For instace, `document.created`, `appeared_in.created`, `item.deleted`. 

## Binding-Key
An  exchange  is  bound  to  queues  through  binding-keys  composed  by  a  *topic-key*  and  a *group-key*.  Messages will be delivered to those queues bound to the exchange with a binding-key that matches  with the routing-key of the message. 

The **topic-key** is defined in the same way that the routing-key, so it is also composed by two words separated by one dot. There are two special cases for matching a topic-key:  
* '`*`': it means that it can be substituted by exactly one word (e.g. `*.created` listen for all the new resources and relations added to the system). 
* '`#`': it means that it can be substituted by zero or more words (e.g. `#` listen for all resources and relations in *any* status).

The **group-key** is a text string that allows different clients to join in the same queue to distribute the  events among them.

Complete examples about routing are shown in the next section “Scenarios”. 

## Messages
Usually,  the  content  of  a  message  is  a  string  of  characters  in  a  *Javascript  Object  Notation*  ([JSON](http://www.json.org/))  format.  But  also,  it  may  be  an  array  of  bytes  serialized  in  a  particular  way.  Our  eventFbus  allows  clients to use both formats. The type of the event, i.e. its routing@key, defines implicity the format of  the message to be understood by both producer and consumer. 
Except  special  cases,  the  message  will  be  a  text  in  JSON  format  with  only  one  field:  the  URI  of  the  resource. 

