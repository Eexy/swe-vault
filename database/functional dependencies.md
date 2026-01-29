---
id: functional dependencies
aliases: []
tags: []
---
# Functional dependencies

A **functional dependency** is a constraint between two set of 
[[relation#attribute|attribute]] $X$ and $Y$ of a [[relation]] $R$ denoted
by $X \rightarrow Y$. The constraint is that for any two [[relation#tuple|tuple]] $t_1$ and 
$t_2$ in $r$ ([[relation#relation#relation-state|relation state]]) that have 
$t_1[X] = t_2[X]$ they must also have $t_1[Y]=t_2[Y]$

This means that the values of $Y$ depends on, or are determined by the values of
$X$

In this case we can say that $Y$ is **functionally dependent** on $Y$

**note**: a functional dependency is abreviated **FD**, $X$ is called the
**left-hand side** and $Y$ the **right-hand side**

A functional dependencies only exist in a relation $R$ if whenever two tuples of
$r(R)$ agree on their $X-values$ also agree on their $Y-values$

**example** : the social security number in a database allow us to determine the
name of a person because all social security number are unique

## Full fonctional dependency

A **full fonctional dependency** $X \rightarrow Y$  is a functional dependency if all attribute of
$X$ are necessary to determined $Y$

## Partial functional dependency

A **partial fonctional dependency** $X \rightarrow Y$ is a functional dependency where we
can remove some attribute of $X$ the dependency still holds

## Transitive functional dependency

A **transitive functional dependency** $X \rightarrow Y$ s a functional
dependency where there is a set of attribute $Z$ that is neighter a candidate
key nor a subset of any key of $R$ and we have  $X \rightarrow Z$ and 
$Z \rightarrow Y$


