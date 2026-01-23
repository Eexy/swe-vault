---
id: union
aliases: []
tags: []
---
# Union

An **union** allow to represent a collection of entites from different
[[entity#entity#entity-type|entity types]] 

An union is as [[subclass & superclass#subclass|subclass]]. This
union correspond to the collection / set of entities that is a subset of the
UNION of all the distinct entity types that forms it. We call this subclass a 
**union type** or a **category**

Because an union is a subclass all the entity types that forms it are its
superclasses

**example** : Let's say that we want to reprent an owner of a vehicule. An owner
could be a PERSON, a COMPANY or a BANK

We need to create a class that includes entities that can come from those 3
entities.

To do that we create a **union type** OWNER that is a subclass of the UNION of
those tree entity sets

### Graphical representation

Here is the [[ER diagram#union|graphical representation]] of the union

