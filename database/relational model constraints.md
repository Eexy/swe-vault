---
id: relational model constraints
aliases: []
tags: []
---
# Relational model constraints

In a [[database state]] we can defined 3 types of constraints

## Implicit constraint

Constraints thare are inherent in the data model

## Explicit constraint

Constraints that can be directly expressed in the schema of the data model by
specifying them in the [[DDL]]

**example**: If we have an [[relation#attribute|attribute]] `age` on our
[[relation]] we can specify that it must be a positive integer

### Domain constraint

The **domain constraint** specify that within each [[relation#tuple|tuple]] the
value of each attribute $A$ must be an atomic value from the domain $dom(A)$

### Key constraint

A [[relation]] is defined as a set of [[relation#tuple|tuple]]. By definition in
a set each element must be unique which be we can't have two tuple with the same
values for each of their attribute

To avoid that we use a subsets of attributes of a
[[relation#relation#relation-schema|relation schema]] $R$ as [[key]]

### Entity integrity constraint

The **entity integrity constraint** states that no primary key value can be
`NULL`. This is because the primary key is used to identify individual tuples in
a [[relation]]

### Referential integrity constraint

The **referential integrity constraint** is specified between two
[[relation|relations]]. It states that one tuple in a relation that reference
another one in an other relation must refer to an existing tuple in that
relation


## Application bases constraints

Application based constraints are constraints that cannot be directly in the
schema of the data model and must be enforced by the application

**example**: We can't enforced a valid email in our data model to achieve this
goal it's the application that will check that the email is semantically correct
