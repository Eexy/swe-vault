---
id: relational algebra
aliases: []
tags: []
---
# Relational algebra

**Relation algebra** allow to manipulate [[relation]] and create new one

Relational algebra is important for 3 reasons:
1. It provide a formal foundation for [[relational model]]
2. It's used as a basis form implementing and optimizing queries
3. Some of its concepts are incorporated into the [[sql]]

## Operations

There is two type of operations

1. operation made exclusively for database
2. operations inherit from set theory

### Exclusive operations

#### SELECT

The `SELECT` operation is used to choose a subset of the tuples from a
[[relation]] that satistfies a **selection condition**

We write the `select` operation like that :

$$
\sigma<condition>(R)
$$

The result of a select operation has the sames [[attribute]] as the [[relation]]

##### Conditions

We can specify the condition in two ways

The first way is to use a constant :

$$
<attribute><operateur><constant>
$$

The second way is to use another attribute :

$$
<attribute><operateur><attribute>
$$

It's also possible to combine conditions with disjonction and conjonction

1. disjonction

$$
<attribute1><operateur><constante1> \ OR \ <attribute2><operateur><constante2>
$$

2. conjunction

$$
<attribute1><operateur><constant1> \ AND \ <attribute1><operateur><constant2>
$$

##### SQL 

```sql
select * 
from employee
where sex = 'female'
```

#### PROJECT

The `PROJECT` operation is used to choose a subset of columns from the
[[relation]]

We write it like that :

$$
\pi <attribute list>(R)
$$

The result of the `PROJECT` operation removes any duplicate tuple. It's like
doing a `DISTINCT`

##### SQL 

```sql
select distinct sex, salary
from employee
```

#### Rename operation

The `RENAME` operation is used to rename either the [[relation]] name or the
[[attribute]] name

We write it like that

$$
\rho_s(B_n)
$$

avec :
- $S$ : new relation name
- $B_n$ : new attribute name

##### SQL

```sql
select E.salary as salary
from employee as e
where e.dno=5
```

#### Nested operations

We can combine operations by either creating temporary result or by nesting
operations

$$
\pi<attribut>(\sigma<condition(R)>)
$$


### Operations inherited

The 3 first operations are binary operations that only applies to two relation and
require that the relations are **compatible** which means that the relations must have the same
[[relation#degree|degree]] and each attribute must have the same domains

#### UNION

The `UNION` is denoted $R \cup U$. It create a relation containing all tuples
from $R$ and $U$

#### INTERSECTION

The `INTERSECTION` is denoted $R \cap U$. It creates a relation containing all
tuples which are in $R$ and in $U$ at the same time

#### Difference

The `DIFFERENCE` is denoted $R \cap U$. It create a new relation with all the
tuple that are in $R$ but not in $U$

#### Cartesian production

The `CARTESIAN PRODUCT` is the only set operation that doesn't need two
compatible relations. We denoted it $R \times U$.

This operation produces a new element by combining every tuple from one relation
with every tuple from the other relation

The result of an `CARTESIAN PRODUCT` is a new relation with a
[[relation#degree|degree]] $n+m$ where $n$ is the degree of the first relation
and $m$ the degree of the second relation

##### SQL

The cartesian product is equivalent to a `CROSS JOIN`

```sql
select * 
from employee 
cross join company
```

### JOIN

The `JOIN` operation is one of the most used operation 

It's denoted 


$$
R_1 \bowtie<condition> R2
$$

Where  :
- $R1$ : first relation
- $condition$ : join condition
- $R2$ : second relation

The `JOIN` operation can be represented like a `CARTESIAN PRODUCT` followed by a
`SELECT`

## Query tree 

![[database/query_tree.png]]

The **query tree** is a tree data structure that corresponds to a relation
algebra expression. It allow us to represent how and in which order the
operations are evaluated

In a query tree each leaf correspond to an operation

