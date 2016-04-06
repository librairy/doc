# Item
An item is each of the elements that make up a document, e.g. the text-content of a file.  It may be the textual content, or an image, or even a workflow. Any media content corresponds with an item. 

It contains the following information: 
* **uri**: the Uniform Resource Identifier created by the system to uniquely identify it. 
* **creation-time**:  date  on  which  this  resource  was  created.  It  must  be  a  formatted  timestamp  following [ISO-8601](http://www.iso.org/iso/home/standards/iso8601.htm). 
* **name**: a label associated to the resource. 
* **description**: additional information about it.  
* **format**: the physical or digital manifestation of the element. It includes the media-type, i.e.  the [IANA](http://www.iana.org/assignments/mediaFtypes/mediaFtypes.xhtml) code. 
* **language**:  the  language(s)  in  which  the  document  is  specified.  It  is  defined  by  [RFC-1766](http://www.ietf.org/rfc/rfc1766.txt)  which  includes  a  two-letter  language  code  followed,  optionally,  by  a  two-letter  country  code. 
* **content**: textual annotation about the file. When it is a paper, it contains the raw-text of the paper. When it is an image, it contains the textual description of the image.


Furthermore, an item may contain zero or more parts. In turn, a part only belongs to one item.  

Since **librairy** can also discover analogies among items, an item may contain zero or more references to other items. 


