# Source
A source is a repository of research objects.  It contains the following information: 
* **uri**: the Uniform Resource Identifier created by the system to uniquely identify it. 
* **creation-time**:  date  on  which  this  resource  was  created.  It  must  be  a  formatted  timestamp  following [ISO-8601](http://www.iso.org/iso/home/standards/iso8601.htm). 
* **name**: a label associated to the resource. 
* **description**: additional information about it.  
* **url**: the Uniform Resource Locator of the repository. 
* **protocol**: defines how the digital content is published. 

A source may contain zero or more references to documents and a document may have one or more  references to sources, i.e. the same document can be available in more than one source. 

![resource-source](https://dl.dropboxusercontent.com/u/299257/librairy/figures/resource-source.png)

It may be a static or a dynamic repository:  
* **Static**: repository that will not change along time. So, once processed, new information will never be available from it again. It can be a single file (e.g. 
`http://world.std.com/~rjs/indinf56.pdf`) or a closed time-based expression for an 
open archive service (e.g. 
`http://www.worldsciencepublisher.org/journals/index.php/AASS/oai?from=2012- 01-01T00:00:00`). 
* **Dynamic**: repository that may have new documents in the future, such as an open archive  publisher (e.g. `http://oa.upm.es/perl/oai2`). This type of resources will  be continuously polled by the hoarder module.

Currently, *The Open Archives Initiative Protocol for Metadata Harvesting* ([OAIFPMH](http://www.openarchives.org/)) and *Really  Simple Sindication* ([RSS](http://www.rssboard.org/rssFspecification)) are the protocols supported by our system. Future integrations will be done  to allow sources such as Dropbox, CIFS/SMB, FTP/FTPS, Elsevier API, Figshare API, arXiv API, DBLP  Corpora, Research Gate, Mendeley and CiteSeer.