# Architecture

**librairy** is a system composed by a loosely-coupled set of services connected by an event bus using standardized data protocols and formats. 

![architecture](https://dl.dropboxusercontent.com/u/299257/librairy/figures/services.png)

It follows a ***Staged Event-Driven Architecture*** ([SEDA](http://www.eecs.harvard.edu/~mdw/proj/seda/)) that decomposes the flow
into a set of stages connected by queues. When a resource (or a relation) change its status, i.e is created or modified or deleted, a new event is published and handled in the system to update it or to build new resources or relationships.

Next we provide a list of services and their responsibility:
* [Explorer](https://github.com/librairy/explorer): deploys a RESTful-web interface to allow executing operations on the system. 
* [Harvester](https://github.com/librairy/harvester-file): retrieves text and meta-information from resources to create domain entities. 
* [LDA-Modeler](https://github.com/librairy/modeler-lda): creates Topic Models based on Latent Dirichlet Allocation (LDA) to represent and categorize domain entities. 
* [W2V-Modeler](https://github.com/librairy/modeler-w2v): creates Word Embeddings representation based on Word2Vec (W2V) to represent and categorize words in a domain. 
* [JSD-Comparator](https://github.com/librairy/comparator-jsd): measures the analogy between domain entities according to Topic Models applying the Jensen-Shannon Divergence.
* [COS-Comparator](https://github.com/librairy/comparator-cos): calculate the cosine similarity for Word Embedding models.
* [Ontology-Learner](https://github.com/librairy/learner-onto): identifies relevant terms and discovers relations among them from a domain. 



