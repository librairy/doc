# Document

A document contains all the meta-information associated to the publication, according to the Open  *Archives Initiative for Object Reuse and Exchange* ([OAIFORE](http://www.openarchives.org/ore/1.0/toc.html)) manifest for research objects and the *Dublin-Core Metadata Annotation* ([DCMI](http://dublincore.org/documents/1999/07/02/dces/)), it include: 
* **uri**: the Uniform Resource Identifier created by the system to uniquely identify it. 
* **creation-time**:  date  on  which  this  resource  was  created.  It  must  be  a  formatted  timestamp  following [ISO-8601](http://www.iso.org/iso/home/standards/iso8601.htm). 
* **publishedOn**:  the  time  the  resource  was  published.  t  must  be  a  formatted  timestamp  following [ISO-8601](http://www.iso.org/iso/home/standards/iso8601.htm). 
* **publishedBy**:  an  entity  responsible  for  making  the  document  available.  It  can  be  a  person,   an  organization  or  a  service.    It  may  be  different  from  the  entity  that  conceptually  formed  the  resource  (e.g.  wrote  the  document),  which  should  be  recorded  as  `authoredBy`.  This  entity  should  be  identified  by  a  valid  Uniform  Resource  Identificator  (URI),  e.g.  [WebId](https://www.w3.org/wiki/WebID),  [orcid](http://orcid.org/) or internal URI. 
* **authoredOn**:    the  time  the  research  was  conceptually  formed.  The  author  time  should  be  present if different from `publishedOn`. It must be a formatted timestamp following [ISO-8601](http://www.iso.org/iso/home/standards/iso8601.htm). 
* **authoredBy**: an entity primarily responsible for making the content of the document. It may  be  a  list  to  indicate  multiple  authors.  Each  of  them  identified  by  a  valid  URI,  e.g.  [WebId](https://www.w3.org/wiki/WebID)  ,  [orcid](http://orcid.org/) or internal URI. 
* **retrievedFrom**:  a  URI  identifying  the  source  from  which  the  document  was  derived.  This  property should be accompanied with `retrievedOn`.  
* **retrievedOn**:  the  time  the  document  was  retrieved  on.  If  this  property  is  present,  then  `retrievedFrom` must also be present. It must be a formatted timestamp following [ISO-8601](http://www.iso.org/iso/home/standards/iso8601.htm). 
* **format**: the physical or digital manifestation of the resource. Typically, it includes the media-type, i.e. the [IANA](http://www.iana.org/assignments/mediaFtypes/mediaFtypes.xhtml) code, of the document. 
* **language**:  the  language(s)  in  which  the  document  is  specified.  It  is  defined  by  [RFC-1766](http://www.ietf.org/rfc/rfc1766.txt)  which  includes  a  two-letter  language  code  followed,  optionally,  by  a  two-letter  country  code. 
* **title**: a name given to the document. It is a name by which the document is formally known. 
* **subject**:  keywords,  key  phrases  or  classification  codes  annotated  by  the  authors  that describe a topic of the resource. 
* **description**: an account of the content of the document. It may include but is not limited to an abstract, or a free-text account of the content. 
* **rights**: information about rights held in and over the document.

Furthermore , a document may contain zero or more items. In turn, an item can belong to one or 
more documents. 

![resource-document](https://dl.dropboxusercontent.com/u/299257/librairy/figures/resource-document.png)

Since **librairy** can also discover analogies among documents, or aggregates other documents,  a document may contain zero or more references to other documents.