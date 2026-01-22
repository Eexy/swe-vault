---
id: specialization & generalization
aliases: []
tags: []
---
# Specialization and Generalization

## Specialization

**Specialization** is the process of defining a set of 
[[subclass & superclass#subclass|subclass]] from a main [[entity#entity#entity-type|entity-type]]

This set of subclasses forms a specialization. It's base on a distinguishing
characterisitic from the main entity

**exemple** : Let's say we have a set of subclass {SECRETARY, ENGINEER,
TECHNICIAN}. This set is a specialization of the superclass EMPLYEE based on the
`job_type` attribute

One thing to take into account we can have multiple specialization based on the
same entity type

## Generalization

**Generalization** is the opposite process of specialization. Instead of
creating a set of sublass from a main entity we create a superclass from the
[[entity|entities]]

## Constraints

All this constraints in this part applies to both specialization and
generalization

### Defining attribute

We can use an [[attribute]] to define to which subclass our entity belongs to.
We say that the specialization / generalization is attribute-defined

**example** : All the EMPLOYEE that have the attribute `job_type=secretary` are
SECRETARY, all the EMPLOYEE that have the attribute `job_type=engineer` ar
engineer

### User-defined

When there is no condition for determining membership in a sublass the subclass
is called **user-defined** which mean that the subclass is defined by the
database users when they apply operation to add an entity to the subclass

### Disjointness constraint

A **disjointess constraint**. This constraint means that an entity can be a member of at most one of the sublass of the
specialization

A specialization that is attribute-defined implies the disjointess constraint

#### Overlapping

When subclasses are not constrained to be disjoint meaning that an entity can
belongs to multiple subclass we say they are overlapping

#### Graphical representation

In a [[ER diagam]] a disjointness constraint is represent by a `d` in a circle on the linked
between the superclass and its subclass

![[database/disjointness_constraint.png]]

When subclass are overlapping we represent this by a `o` instead of a `d`

![[database/overlapping_subclass.png]]

### Completeness constraint

A **completeness constraint** also called a **totalness constraint**. This constraint can be partial or total.

There is two forms of a completeness constraint

- total: it means that every entity of the superclass must be a member of at
least one subclass
- partial: it means that not every entity must belong to a subclass

#### Graphical representation

A total specialization / generalization is represented by two straigth lines

A partial specialization / generalization is represented by one straigth line

There is two example above on the disjointness constraint graphical
representation
