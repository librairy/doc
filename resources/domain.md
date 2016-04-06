# Domain
A domain is a logical grouping of documents. It defines the workspace for the modeler and the  learner module. By default, all sources have an associated domain with their documents. 

It contains the following information: 
* **uri**: the Uniform Resource Identifier created by the system to uniquely identify it. 
* **creation-time**:  date  on  which  this  resource  was  created.  It  must  be  a  formatted  timestamp  following [ISO-8601](http://www.iso.org/iso/home/standards/iso8601.htm). 
* **name**: a label associated to the resource. 
* **description**: additional information about it.  

![resource-domain](https://dl.dropboxusercontent.com/u/299257/librairy/figures/resource-domain.png)

A domain can contain zero or more references to documents and a document may be referenced by one or more domains. 