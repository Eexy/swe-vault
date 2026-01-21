---
id: relationship
aliases: []
tags: []
---
# Relationship

## Relationship type, relationship set and instances

A **relationship type** $R$ among $n$ [[entity#entity#entity-type|entity type]] $E1, E2,...,E_n$ define a set of
association or a **relationship set** among entities from these entity type

Mathematically the relationship set $R$ is a set of **relationship instances**
$r_i$, where each $r_i$ associates $n4 individual entities ($e_1$, $e_2$, ...
,$e_n$). Hence a relationship set is a mathematical [[relation]]

Alternatively it can also be defined as a subset of the cartisian product of the
[[entity#entity-set--entity-collection|entity set]]

Each entity is said present in the relationship type is said to **participate**

## Relationship degree

The **relationship degree** is the number of entity type participating in the
relationship

## Role name

Each entity type that participate to the relationship play a **role**

**exemple** : Imagine a relationship WORKS FOR the EMPLOYEE entity play the role
of employee or worker and department play the role of department or employer

A role is not something necessary specially in a relationship where each entity
are distinct but in **recursive relationship** it's important that each entity
has a role

## Recursive relationship

A **recursive relationship** is a relationship where an entity participate
multiple times

**exemple** : A relationship WORKS FOR. In this relationship an EMPLOYEE can be
a worker but also the director

## Cardinality ratio

The **cardinality ratio** define the maximum number of relationship
instances that an entity can participate in

The most common relationship is a **binary relationship**. In a binary
relationship we can have those cardinality ratio


- `1:N` : An entity instance $A$ can be associated to multiple entity instances $B$ (One-to-many)
- `N:1` : Multiple entities instance $A$ can be to one entity $B$ (Many-to-one)
- `1:1` : A entity instance $A$ is associated to one entity instance $B$ (One-to-one)
- `M:N` Multiple entity instance $A$ can be associated to multiple entity
instance $B$ (Many-to-many)

## Participation constraint

A **participation constraint** definie the minimun number of relationship
instances that each entity can participate in. It can also be called **minimum
cardinality constraint**

### Total participation

A participation is a **total participation** if all entity instance of the
entity type $E$ is must participate to a relationship $R$

### Partial participation

A participation is a **partial participation** if not all entity instance are
required to participate to the relationship $R$

