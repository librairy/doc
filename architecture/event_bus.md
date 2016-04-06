# Event Bus
Following a publisher/subscriber approach, all the modules in the system can publish and read  events to notify and to be notified about the system state. 

For example, when a new domain is created, an event-message will be published to the channel:  `domain.created`. This event will be managed by the learner module to begin to analyze all the  items in that domain and also by the modeler module to begin to build models which represent  these items. Therefore, the system flow is not unique and is not directly implemented, instead  parallel and emergent flows can appear according to particular actions on resources. 

We use the *Advanced Message Queuing Protocol* ([AMQP](http://www.amqp.org/)) as our messaging standard to avoid any  cross-platform problem and any dependency to the selected message broker. This protocol defines  the following elements: `exchange`, `queue` and `routing-key`. 

In this scenario, a *producer* module sends a message to the `exchange` element, instead of a `queue`,  along with a `routing-key`. That `exchange` may be bound to `queues` through *topic* and *group* bindings defined by a module. A *topic binding* is a directive indicating what messages should be routed from an `exchange` to a `queue`. The *group binding* allows system to deliver a message only  to one *consumer* sharing the same *group* value, getting a dynamic distribution of load between them. 
