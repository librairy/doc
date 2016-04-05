# Resources

The system is updated with both gathered and submitted information internally modeled as  resources. A resource is an abstract representation of the information described by the type of  content and the status. 

![Resources](https://dl.dropboxusercontent.com/u/299257/librairy/figures/data-modelv0.2.png)

The states are common for all, but the type of content depends on each of them: 
* **Source**: repository of *documents*.
* **Domain**: set of *documents*. It can contain *documents* from different *sources*.
* **Document**: meta-information retrieved from a file. A document can bundle a set of *items* or can aggregate other *documents*.
* **Item**: each of the elements that make up a *document* when it is a file, not when it is a composition of files. It describes a kind of content of the *document*.
* **Part**: logical division inside an item based on aspects such as sections of the article  (i.e. abstract , introduction, method, results, discussion and conclusion) or the rhetorical class  of the sentences (i.e. approach, background, challenge, future@work and outcome).
* **Word**: a minimum textual unit that composes a text.
* **Term**: combination of one or more *words* offering a sense in a *domain*.
* **Topic**: abstract  concept  described  by  a  set  of  *words*  that  represents  an area  or  subject in a *domain*. 

The next figure tries to clarify the distinction between `documents` and `items`. A `document` describes a file not the content, and may aggregates more documents as far as contains new files inside. Instead, an `item` is an abstract entity containing only one kind of data (e.g. text, image, workflow, etc) retrieved from a document.

![paper](https://dl.dropboxusercontent.com/u/299257/librairy/figures/paper-to-resources.png)