---
id: relation
aliases: []
tags: []
---
# Relation

the [[ER model]] represent the database as a collection of **relation**. A
relation is a **table** where each row represents a collection of related
data values. 

A row typically corresponds to a [[entity|entity instance]] or [[relationship|relationship instance]] and it's called
a **tuple**

Each relation owns a name which is the table name and columns name that are used
to help interpret the meaning of the values in each row

The columns are the **[[#Attribute|attributes]]** of the relations

**example** : A relation STUDENT. Each tuple of this relation represents a real
student

## Domains

A **domain** $D$ is a set of **atomic value** which mean that each value in the
domain is indivisible as far as the formal relational model is concerned.

One way to create a domain is to specify a data type from which the values
forming the domain are down

**example** : Let's say we have a relation STUDENT it could have a `age`
domain. This age attribute is of type integer

## Relation schema

A **relation schema** $R$ discribe the relation we write it

$$
R(A_1, A_2,...,A_n)
$$

We have :

- $R$ as the name of the relation
- $A_i$ the list of [[#Attribute|attribute]] which correspond to a
[[#Domains|domain]]

## Attribute

An **attribute** $A_i$ is the name of a role played by some domain $D$ in the
relation schema $R$. We say that $D$ is **domain** of $A_i$ and we write it

$$
dom(A_i)
$$

**example** : An `age` attribute represent the domain of all positive integer in
our relation

### Prime attribute

A **prime attribute** is an attribute that is a member of a
[[key#candidate-key|candidate key]]

## Degree

The **Degree** of the relation corresponds to the number of attributes in our
relation

## Tuple

A tuple is a list of $n$ ordered values


$$
t = <v_1, v_2,...,v_n>
$$

Each $v_i$ is an element of $dom(A_i)$ or the $NULL$ value

In a tuple the $i$th value corresponds to the attribute $A_i$ and is referred to as $t[A_i]$ 

## Relation state

A **relation state** also called **relation** $r$ of the relation $R(A_1,...,A_n)$ is written

$$
r(R)
$$

It correspond to set of $n$-[[#Tuple|tuple]] that we can write

$$
r = {t_1, t_2,...,t_n}
$$

## Mathematical representation

A relation can be represented as a mathematical relation of degree $n$ which is
a subset of the cartesian product of the domains that define $R$

$$
r(R) \subseteq (dom(A_1) \times dom(A_2) \times ... dom(A_n))
$$

