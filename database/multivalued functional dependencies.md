---
id: multivalued functional dependencies
aliases: []
tags: []
---
# Multivalued functional dependency

A **multivalued functional dependency** is a [[functional dependencies]] denoted
by $X \twoheadrightarrow Y$  on a [[relation]] $R$ where $X$ and $Y$ are both
subsets of $R$ and $X$ determine a set of possibles values for $Y$ independently
of other attributes in the relation. Contrary to a normal functional dependency where 
$X$ determine directly the values of $Y$

The formal definition is :

We have a multivalued functional dependency $X \rightarrow Y$ specified on a [[relation]] $R$ where $X$, $Y$ and $Z$ 
are set of [[relation#attribute|attributes]] of $R$ and $Z = R-(X \cup Y)$

if it exist 4 tuples $t_1$, $t_2$, $t_3$ and $t_4$

$$
t_3[X] = t_4[X] = t_2[X] = t_1[x]
$$
$$
t_3[Y]=t_1[Y] \ and \ t_2[Y]=t_4[Y]
$$
$$
t_3[Z]=t_2[Z] \ and \ t_1[Z]=t_4[Z]
$$

With this definition we see that there is multiple values for $Y$ because $Y$
can take the values from $t_1$ or from $t_2$. We also see with this definition
that there is a swap of values on $Z$

**example**: A `TEACHER` relation


| Tuple | Professor | Course | Hobby |
|-------|-----------|---------|---------|
| t1 | Dr. Smith | Databases | Tennis |
| t2 | Dr. Smith | Networks | Reading |
| t3 | Dr. Smith | Databases | Reading |
| t4 | Dr. Smith | Networks | Tennis |

We can see that for `Course` and or `Hobby` we have multiple possible values for Dr.Smith

## Trivial and Nontrivial

A multivalued functional dependency is called **trivial** if $Y$ is a subset of
$X$ or if the union of $X$ and $Y$ is equal to the set of attribute of $R$ $X \cup Y = R$

If the multivalued functional dependency doesn't satisfies one of this clause we
said that it's **nontrivial** which means there is redundancy like in the `TEACHER` relation

