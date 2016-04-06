# Word
A word is the smallest meaningful unit contained in a text. 

It contains the following information: 
* **uri**: the Uniform Resource Identifier created by the system to uniquely identify it. 
* **creation-time**:  date  on  which  this  resource  was  created.  It  must  be  a  formatted  timestamp  following [ISO-8601](http://www.iso.org/iso/home/standards/iso8601.htm). 
* **content**: lemma, i.e the word which stands at the head of a definition in a dictionary. 

Furthermore, a word is embedded in one or more domains. In turn, a domain can contain zero or more words.
