# Requirements for demo:
- pp api description available to client
- pp api wrapper
- client implementation
  - java
  - shacl lib, minor tweaks


## Summary:

### Server:
Hydra description of pp api
  - diff types: added, deleted 
  - return: shape of the returned data
  - description of the shape of the diff of a certain type
  - necessary parameters for IRI template
- skos-api metamodel (extending skos)


### Client:

* 1 Data/State is expressed in terms of the skos-api metamodel
* 2.a Client decides added and/or deleted diff between current and desired state.
  * 2.a.1 Client matches diffs to corresponding server description diff shapes.
  * 2.a.2 Gets set of operations
  * 2.a.3 for each operation, determine optimal one:
    * 2.a.3.1 Client determines necessary params.
    * 2.a.3.2 if yes, continue to  
    * 2.a.3.3 if no, bla
  * 2.a.4 if no operation found throw error
  * 2.a.5 we now have a set of operations
  * 2.a.5.1 for each operation:
  * 2.a.5.1.1 simulate:(figure out what the operation's effect is on your current state) 
  * 2.a.5.1.1.1 combine current state with inferred new state 
  * 2.a.5.1.2 if goal is complete: execute best operation
  * 2.a.5.1.2 if goal is not complete: go to 2.a.3
* 2b Client matches retrieval goal with return shape of server description
  * similar

**Challenge:**

After a mutation, the changes may not be returned, so client would have to retrieve said changes.
  - Solution: Generic client only supports skos-api metamodel. Shape describing resulting state of operation should contain complete description of state change.
