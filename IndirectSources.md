### Indirect Sources ###

(TBA)


#### Storage Object ####

HTML 5 Storage objects [[6](#References.md)][[7](#References.md)][[8](#References.md) ] can be considered an indirect source, since they can be used to store values from direct sources and use them later insecurely.

Indirect source objects are:

  * localStorage
  * sessionStorage
  * IndexedDB (mozIndexedDB, webkitIndexedDB, msIndexedDB)
  * Database (Safari Only)

#### Server Response Sources ####

Previously server side stored data could be used by an attacker to send untrusted input
to Javascript.

(TBF)