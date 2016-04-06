# Librairy Tutorial

This Doc is build for researchers so that it's easier to use and extend Librairy v0.3. Built using [Gitbook](https://github.com/GitbookIO/gitbook).

## Librairy

*Librairy* is a service-oriented platform that aims to simplify the construction of large scale text-analyzers. It is a collection of Natural Language Processing (NLP) tasks, machine learning algorithms and semantic techniques distributed as services to compose a combined solution. 

It allows users to easily deploy services, so that they can reuse them in their deployments or even incorporate new algorithms to share with other users. 

### Framework Architecture

In this way, you are not required to use all of services just because you want to use some of them. You can pick and choose which services you want to use. This allows you to work with other tools easily. It also means that you are not required to engage in an all-or-nothing deployment to begin using *librairy*.

All services have been built by using the [Boot](https://github.com/librairy/boot) library. It encapsulates all the particularities required by the system, offering a more friendly interface. Also, a Restful-HTTP service named [Explorer](https://github.com/librairy/explorer) is available supporting similar functionality in a less coupled way. 


### Key Benefits

* Scalable: applications are built in modules, and with event-driven architecture
* Sensible defaults: Underscore templates are used for view rendering
* Easily modifiable: make it work with your application's specific needs
* Reduce boilerplate for views, with specialized view types
* Build on a modular architecture with an `Application` and modules that attach to it
* Compose your application's visuals at runtime, with the `Region` and `Layout` objects
* Nested views and layouts within visual regions
* Built-in memory management and zombie-killing in views, regions and layouts
* Event-driven architecture with `Backbone.Wreqr.EventAggregator`
* Flexible, "as-needed" architecture allowing you to pick and choose what you need
* And much, much more


[Read-more](https://www.gitbook.com/book/cbadenes/librairy-tutorial/details)