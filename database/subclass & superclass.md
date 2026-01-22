---
id: subclass & superclass
aliases: []
tags: []
---
# Subclass & superclass

## Subclass

A **subclass** is a subtype of an [[entity]] that have a special meaning /
specific role

A subclass inherit all the [[attribute]] and [[relationship]] from the entity but can also
have its own attribute / relationship. 

When a subclass has its own attribute / relationship it can be considered an
[[entity#entity#entity-type|entity type]] in its own right

**example** : Let's say we have an entity type EMPLOYEE we can have a subclass
SECRETARY, ENGINEER. All those subclass not necessery exist as en entity type

## Superclass

A **superclass** is the main type from which the subclass derived

## Graphical representation


### ER diagram

![[database/subclass.png]]

In a [[ER diagam]] a subclass is represented like a entity linked to
the main entity.

If the subclass has its own attribute then like an entity we represented like
any attribute in an entity

For subclass we only specified its own attribute we don't need to represented
all the inherited attribute

### UML diagram

![[database/subclass_uml.png]]

In a [[UML diagram]] like in a ER diagram a subclass is represented like an
normal enity linked to the main entity with a solid line. There is the an arrow on
the going to the superclass 


