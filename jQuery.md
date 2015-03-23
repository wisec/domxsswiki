# jQuery #


## List of Sinks ##

#### Global jQuery Functions ####
The following sinks allow HTML injection:
  * **jQuery( _htmlText_ `[`, ownerDocument`]`  )** and **$( _htmlText_ `[`, ownerDocument`]`  )** : if the first argument contains a pattern that matches with some known tag it'll be created a HTML fragment. [Reference](http://api.jquery.com/jQuery/#jQuery2).
    * **Update**: as of version 1.6.1 this is exploitable only if the _htmlText_ **does not** start with #.
    * **Update2**: as of version 1.9.0 this is exploitable only if the _htmlText_ starts with '<'.
  * **jQuery.parseHTML(_htmlText_)**: static method introduced on version 1.8.0 which uses DIV.innerHTML to parse HTML using the browser parser. (thanks to Gareth Heyes for pointing this out).

The following sinks allow JavaScript execution:
  * **jQuery.globalEval( _userContent_ )**: equivalent to eval sink. [Reference](http://api.jquery.com/jQuery.globalEval/)

#### element-specific functions ####
  * element.**add( _userContent_ )**: adds elements to the matched elements. [Reference](http://api.jquery.com/add/)
  * element.**append( _userContent_ )** : inserts given HTML at the end of each matched element. [Reference](http://api.jquery.com/append/)
  * element.**after( _userContent_ )** :  inserts given HTML after each matched element. [Reference](http://api.jquery.com/after)
  * element.**before( _userContent_ )** : inserts given HTML before each matched element. [Reference](http://api.jquery.com/before)
  * element.**html( _userContent_ )** : equivalent in assigning element.innerHTML = usercontent. [Reference](http://api.jquery.com/html/#html2)
  * element.**prepend( _userContent_ )** : inserts given HTML at the beginning of each matched element. [Reference](http://api.jquery.com/prepend)
  * element.**replaceWith( _userContent_ )** : replace each element with the given new content.  [Reference](http://api.jquery.com/replaceWith)
  * element.**wrap( _userContent_ )** : wrap element(s) within given HTML. [Reference](http://api.jquery.com/wrap)
  * element.**wrapAll( _userContent_ )** : wrap element(s) within given HTML. [Reference](http://api.jquery.com/wrapAll)

  * **In general**, every function that accepts the **htmlString** type (see [jQuery docs](http://api.jquery.com/Types/#htmlString)). (TODO: Extract these from their docs)


**Warning:** This list is still far from being complete.