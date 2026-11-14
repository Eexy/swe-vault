---
id: relation
aliases: []
tags: []
---

# Relation

Let $A$ and $B$ be [[set|sets]]. A **relation** $R$ form $A$ to $B$ is a subset
of the [[cartesian product]] of $A$ and $B$.

Given an [[ordered tuple#ordered-pair|ordered pair]] $(x,y)$ in $A \times B$, $x$ is
related to $y$ by $R$, written $x R y$ if and only if $(x,y)$ is in $R$.

The set $A$ is called the **domain** of $R$ and the set $B$ is called its
**co-domain**

The notation for a relation $R$ may be written as follows :

$$
x R y \ means \ that \ (x,y) \in R
$$

**example** : Let $A = \{1, 2, 3\}$ and $B = \{a, b\}$. The following is a valid
relation from $A$ to $B$:

$$
R = \{(1,a),\ (2,b),\ (3,a)\}
$$

Here $1 R a$, $2 R b$, and $3 R a$

**example** : The "less than" relation on $\mathbb{Z}$: $x R y$ means $x < y$, so
$(1,2) \in R$, $(2,5) \in R$, but $(3,1) \notin R$

## Inverse relation

Let $R$ be a relation form $A$ to $B$. Define the inverse relation $R^{-1}$ form $B$ to $A$ as follows

$$
R^{-1} = {(y,x)} \in B \times A | (x,y) \in R
$$

## Directed graph

A relation on a set $A$ is a relation from $A$ to $A$

When a relation $R$ is defined on a set $A$, the arrow diagram of the relation can be modified so that it becomes a [[directed graph]]. Instead of representing $A$ as two separate sets of points, represent $A$ only once, and draw an arrow from each point of $A$ to each related point

Example : Let $A = \{ 3,4,5,6,7,8\}$ and define a relation $R$ on $A$ as follows: For every $x,y \in A$ we have

$$
x R y \leftrightarrow 2|(x-y)
$$

![[relation_directed_graph.png]]

## N-ary relations

A special group of relations, called $n$-ary relations, form the mathematical foundation for relational database theory. Just as binary relation is a subset of a [[cartesian product]] of two sets, an $n$-ary relation is a subset of a cartesian product of $n$ sets

Here is the formal definition :

Given sets $A_1, A_2,..., A_n$ an $n$-ary relation $R$ on $A_1 \times A_2 \times ... \times A_n$ is a subset of $A_1 \times A_2 \times ... \times A_n$. The special cases of $2$-ary, $3$-ary and $4$-ary relations are called **binary**, **ternary**, and **quarternary relations**, respectively

## Reflexivity, Symmetry and transitivity

Let $R$ be a relation on a set $A$

1. $R$ is **reflexive** if, and only if, for every $x \in A, x R x$
2. $R$ is **symmetric** if and only if, for every $x, y \in A$, if $x R y$ then $y R x$
3. $R$ is **transitive** if, and only if, for every $x,y,x \in A$, $x R y$ and $y R z$ then $x R z$

In other term

1. **Reflexive** : each element is related to itself
2. **Symmetric** : If any one element is related to any other element, then the second element is related to the first
3. **Transitive** : If any one element is related to a second and that second element is related to a third, then the first element is related to the third

Those definitions are universal [[statement]]. This means that to prove a relation has one of the properties you use either the [[direct proof#Generalizing from the Generic Particular| method of generalizing]] or [[direct proof#Method of exhaustion|the method of exhaustion]]

Here is an example of a relation statisfying all those properties

![[reflexivity_symmetry_transitive_relation.png]]

#### Proof example

Here is an example of proof for those 3 properties

Example :

We define a relation $T$ on $Z$ (the set of all integer) as follows : For all integers $m$ and $n$

$$
m T n \leftrightarrow 3|(m-n)
$$

We must prove that the relation is transitive, reflexive and symmetric

**T is reflexive** : To show that $T$ is reflexive, it is necessary to show that

$$
\text{ for every } m \in Z, mTn
$$
By definition of $T$, this means that 

$$
\text{For every } m \in Z, 3|(m-n)
$$
Which is true because $m-m = 0$ and $3 | 0$. Hence T is reflexive

**T is symmetric** : To show that $T$ is symmetric, it is necessary to show that

$$
\text{ For every } m,n \in Z, \text{ if } mTn \text{ then } n T m
$$
By definition of $T$ this means that

$$
\text{ For every } m,n \in Z, \text{ if } 3|(m-n) \text{ then } 3|(n-m)
$$

We suppose $m$ and $n$ are particular but arbitrarily chosen integers such that $3|(m-n)$ can we find an integer  $k$ so that $n-m = 3 \cdot k$

By definition of "divides" since

$$
3|(m-n)
$$
then

$$
m-n = 3 \cdot k
$$
The crucial observation is that $(n-m) = -(m-n)$. Hence we can multiply both sides of this equation by $-1$ to obtain

$$
-(m-n) = -3k
$$
$$
n-m = 3(-k)
$$
Since $-k$ is an integer this equation shows that

$$
3 | (n-m)
$$

So it follows that $T$ is symmetric

**T is transitive** : To show that $T$ is transitive, it is necessary to show that


$$
\text{ For every } m,n, p \in Z, \text{ if } mTn \text{ and } nTp \text{ then } mTp
$$
By definition of T this means


$$
\text{ For every } m,n \in Z, \text{ if } 3|(m-n) \text{ then } 3|(m-p)
$$

Suppose $m, n$ and $p$ are particular but arbitrarily chosen integers such that $3|(m-n)$ and $3|(n-p)$ can we find an integer $k$ such that $m-p = 3 \cdot k$

By definition of divides

$$
3 | (m-n) \text{ and } 3|(n-p)
$$

then

$$
m-n = 3r \text{ for some integer } r 
$$
and

$$
n-p =3s \text{ for some integer } s
$$

The crucial observation is that $(m-n)+(n-p) = m-p$. We add these two equations together to obtain

$$
(m-n) + (n-p) = 3r+3s
$$
which is equivalent to

$$
m-p = 3(r+s)
$$

Since $r$ and $s$ are integer, $r+s$ is an integer. To this equation shows that

$$
3|(m-p)
$$

So it follows that $T$ is transitive

## The transitive closure of a relation

Generally speaking, a relation fails to be transitive because it fails to contain certain ordered pairs. To obtain a transitive relation from one that is not transitive, it is necessary to add ordered pairs.

Roughly speaking, the relation obtained by adding the least number of ordered pairs to ensure transitivity is called the *transitive closure* of the relation. More precisely, the transitive close of a relation is the smallest transitive relation that contains the relation

More formally it is defined as follow :

Let $A$ be a set and $R$ a relation on $A$. The **transitive closure** of $R$ is the relation $R^t$ on $A$ that satisfies the following three properties

1. $R^t$ is transitive
2. $R \subseteq R^t$
3. If $S$ is any other transitive relation that contains $R$, the $R^t \subseteq S$
