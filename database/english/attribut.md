---
id: attribute
aliases: []
tags: []
---
# attribute

An **attribute** is a property of an [[entity]]. Each attribute has a value

## Composite and atomic attribute

A composite attribute is an attribute that can be divided into smaller subpart

**exemple** : an address attribute can be divided like thath :

- street's name
- street's number
- zip code
- city

An **atomic attribute** is an attribute that can't be divided

**exemple** : We can't divide a name

## Single-valued and multivalued attribute

A **single valued attribute** is an attribute that can only contains one value

**exemple** : an `age` attribute can only contains one numer

A **multivalued attribute** is an attribute that can contains multiple value at
the same time

**exemple** : An attribute `color` on a car entity can contains multiple values
for each color the cas has

## Stored and derived attribute

A **stored attribute** is a attribute that is save into the db

A **derived attribute** is an attribute that can be derived from another one

**exemple**: We can derived an `age` attribute fron a `birthdate` attribute so
that we only store the last one

## NULL values

A **nullable attribute** is an attribute that can have the `NULL` value

## Domain

Each attribute is associated with a **domain**

A domain is the set of all possible values

Mathematically an attribute $A$ of an entity set $E$ whose domain is $V$ can be defined from $E$ to the
power set $P(V)$ of $V$

$$
A : E \rightarrow P(V)
$$

We refer to the value of attribute $A$ for an entity $e$ s $A(e)$

When we are talking about a composite attribute its domain $V$ is equal to the
power of set of the cartesian product of the sets of all the simple component attributes that form
$A$

$$
V = P(P(V_1)\times P(V_2)...\times P(V_n)
)$$


