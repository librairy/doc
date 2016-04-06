# Document

A document contains all the meta-information associated to the publication, according to the Open  *Archives Initiative for Object Reuse and Exchange* ([OAIFORE](http://www.openarchives.org/ore/1.0/toc.html)) manifest for research objects and the *Dublin-Core Metadata Annotation* ([DCMI](http://dublincore.org/documents/1999/07/02/dces/)), it include: 
* **uri**: the Uniform Resource Identifier created by the system to uniquely identify it. It must be  a Universally Unique Identifer (UUID) along with a prefix identifying the type of the resource:  e.g documents/de305d54-75b4-431b-adb2-eb6b9e546014 
* **creation-time**:  date  on  which  this  resource  was  created.  It  must  be  a  formatted  timestamp  following ISOF8601. 
* **publishedOn**:  the  time  the  resource  was  published.  t  must  be  a  formatted  timestamp  following ISOF8601. 
* **publishedBy**:  an  entity  responsible  for  making  the  document  available.  It  can  be  a  person,   an  organization  or  a  service.    It  may  be  different  from  the  entity  that  conceptually  formed  the  resource  (e.g.  wrote  the  document),  which  should  be  recorded  as  authoredBy.  This  entity  should  be  identified  by  a  valid  Uniform  Resource  Identificator  (URI),  e.g.  WebId15,  orcid16 or internal URI. 
* **authoredOn**:    the  time  the  research  was  conceptually  formed.  The  author  time  should  be  present if different from publishedOn. It must be a formatted timestamp following ISOF8601. 
* **authoredBy**: an entity primarily responsible for making the content of the document. It may  be  a  list  to  indicate  multiple  authors.  Each  of  them  identified  by  a  valid  URI,  e.g.  WebId17  ,  orcid18 or internal URI. 
* **retrievedFrom**:  a  URI  identifying  the  source  from  which  the  document  was  derived.  This  property should be accompanied with retrievedOn.  
* **retrievedOn**:  the  time  the  document  was  retrieved  on.  If  this  property  is  present,  then  retrievedFrom must also be present. It must be a formatted timestamp following ISOF8601. 
* **format**: the physical or digital manifestation of the resource. Typically, it includes the mediaF type, i.e. the IANA19 code, of the document. 
* **language**:  the  language(s)  in  which  the  document  is  specified.  It  is  defined  by  RFCF176620  which  includes  a  twoFletter  language  code  followed,  optionally,  by  a  twoFletter  country  code. 
* **title**: a name given to the document. It is a name by which the document is formally known. 
* **subject**:  keywords,  key  phrases  or  classification  codes  annotated  by  the  authors  that 
describe a topic of the resource. 
* **description**: an account of the content of the document. It may include but is not limited to  an abstract, or a freeFtext account of the content. 
* **rights**: information about rights held in and over the document.