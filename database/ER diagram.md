---
id: ER diagram
aliases: []
tags: []
---
# ER diagram

![[Pasted image 20250316151902.png]]

## Entity

An [[entity]] is represented by a rectangle

### Weak entity

A [[entity#weak-entity|weak entity]] is represented by a rectangle but with two
border

## Attribute

An [[attribute]] is represented by a cercle with the name and a link to the
entity

### Composite attribute

A [[attribute#composite-and-atomic-attribute|composite attribute]] is
represented like an attribute with different attribute linked to him

### Multivalued attribute

A [[attribute#single-valued-and-multivalued-attribute|multivalued attribute]] is represented like an attribute with a cercle with two border

### Derived attribute

A [[attribute#stored-and-derived-attribute|derived attribute]] is represented
like an attribute with a dotted border

## Key

A [[key]] is represented like an underlined attribute

## Relationship

A [[relationship]] is represented with a diamond shape box with its name in the
center an linked to the entities

### Total participation

A [[relationship#participation-constraint#total-participation|total
participation]] is represented like a relationship but with two linked to the
entity

### Partial participation

A [[relationship#participation-constraint#partial-participation|partial
participation]] is represented like a relationship 

## Subclass & superclass

![[database/subclass.png]]

In a ER diagram a subclass is represented like a entity linked to
the main entity.

If the subclass has its own attribute then like an entity we represented like
any attribute in an entity

For subclass we only specified its own attribute we don't need to represented
all the inherited attribute

### Constraints

In a ER diagram a disjointness constraint is represent by a `d` in a circle on the linked
between the superclass and its subclass

![[database/disjointness_constraint.png]]

When subclass are overlapping we represent this by a `o` instead of a `d`

![[database/overlapping_subclass.png]]

A total specialization / generalization is represented by two straigth lines

A partial specialization / generalization is represented by one straigth line

### Union

An [[union]] is represented like an entity connected to all the entity types
with a `u` in a circle and a $\cup$

![[database/union.png]]

