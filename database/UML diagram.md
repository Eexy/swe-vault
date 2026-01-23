---
id: UML diagram
aliases: []
tags: []
---
# UML diagram

![[database/UML diagram.png]]

## Entity

An [[entity]] is represented by a box with two section

- first section : the name of the entity
- second section : the list of [[attribute|attributes]]

## Attribute

An [[attribute]] is represented by its name in the second section of the
entity's box

### Composite attribute

A [[attribute#composite-and-atomic-attribute|composite attribute]] with is name
and next to it all attribute that compose him

### Multivalued attribute

A [[attribute#single-valued-and-multivalued-attribute|multivalued attribute]] is
considered as an entity so it have its own box

## Relationship

In a UML diagram a [[relationship]] is called an **association** and a instance
a **link**

A binary association is represented by a solid line between the two entity. On
or under the line there is the name of the relationship

The [[relationship#cardinality-ratio|cardinality ratio]] is represented on both
side by the **multiplicities**. 

The multiplicites must be written like that `min..max`. If the max side doesn't
have any limit it's replace by an asterisk `*` or by `n`

**important** : The multiplicities is placed on the opposite side of the entity

**exemple** : multiplicities between a product and its categories

![[database/multiplicities.png]]

## Subclass and superclass

![[database/subclass_uml.png]]

In a [[UML diagram]] like in a ER diagram a subclass / superclass is represented like an
normal enity linked to the main entity with a solid line. There is the an arrow on
the going to the superclass 


