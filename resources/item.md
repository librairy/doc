# Item
An item is each of the elements that make up a document, e.g. the text-content of a file.  It may be the textual content, or an image, or even a workflow. Any media content corresponds with an item. 

It contains the following information: 
* **uri**: the Uniform Resource Identifier created by the system to uniquely identify it. 
* **creation-time**:  date  on  which  this  resource  was  created.  It  must  be  a  formatted  timestamp  following [ISO-8601](http://www.iso.org/iso/home/standards/iso8601.htm). 
* **name**: a label associated to the resource. 
* **description**: additional information about it.  
* **format**: the physical or digital manifestation of the element. It includes the media-type, i.e.  the [IANA](http://www.iana.org/assignments/mediaFtypes/mediaFtypes.xhtml) code. 
* **language**: the language(s) in which it is specified. It is defined by RFCF176624 which includes a  twoFletter Language code followed, optionally, by a twoFletter country code. 

