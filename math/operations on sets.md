---
id: operations on sets
aliases: []
tags: []
---
# Operations on sets

There exists multiple operations on [[set]]

Let $A$ and $B$ be subsets of a universal set $U$

1. The **union** of $A$ and $B$, denoted $A \cup B$ is the set of all elements
   that are in at least one of $A$ or $B$
2. The **intersection** of $AA$ and $B$, denoted $A \cap B$ is the set of all
   elements that are in common to both $A$ and $B$
3. The **difference** of $B$ minus $A$ (also called the **relative complement**
   of $A$ in $B$) denoted $B - A$ is the set of all elements that are in $B$ and
   not $A$
4. The **complement** of $A$ denoted $A^c$ is the set of all elements in $U$
   that are not in $A$

## Interval notation

When working with the set of [[set#common-set|real number]] we can use the
**interval notation** to represent its subset

Given real numbers $a$ and $b$ with $a \le b$:

$$
(a, b) = \{x \in \mathbb{R} \mid a < x < b\} \qquad [a, b] = \{x \in \mathbb{R} \mid a \le x \le b\}
$$
$$
(a, b] = \{x \in \mathbb{R} \mid a < x \le b\} \qquad [a, b) = \{x \in \mathbb{R} \mid a \le x < b\}
$$

The symbols $\infty$ and $-\infty$ are used to indicate intervals that are unbounded either on the right or on the left:

$$
(a, \infty) = \{x \in \mathbb{R} \mid x > a\} \qquad [a, \infty) = \{x \in \mathbb{R} \mid x \ge a\}
$$
$$
(-\infty, b) = \{x \in \mathbb{R} \mid x < b\} \qquad (-\infty, b] = \{x \in \mathbb{R} \mid x \le b\}
$$

## Operation on multiple set

The union and intersection of sets are also defined when working with more that 2 sets

Given sets $A_0, A_1, A_2, \ldots$ that are subsets of a universal set $U$ and given a nonnegative integer $n$:

$$\bigcup_{i=0}^{n} A_i = \{x \in U \mid x \in A_i \text{ for at least one } i = 0, 1, 2, \ldots, n\}$$

$$\bigcup_{i=0}^{\infty} A_i = \{x \in U \mid x \in A_i \text{ for at least one nonnegative integer } i\}$$

$$\bigcap_{i=0}^{n} A_i = \{x \in U \mid x \in A_i \text{ for every } i = 0, 1, 2, \ldots, n\}$$

$$\bigcap_{i=0}^{\infty} A_i = \{x \in U \mid x \in A_i \text{ for every nonnegative integer } i\}$$

## Disjoint sets

Two sets are called **disjoint** if and only if they habe no elements in common 

Symbolically

$$
A \text{ and } B \text{ are disjoint } \iff A \cap B = \emptyset
$$

## Partition of set

A finite or infinite collection of nonempty sets $\{A_1, A_2, A_3, \ldots\}$ is a **partition** of a set $A$ if and only if:

1. $A$ is the union of all the $A_i$
2. the sets $A_1, A_2, A_3, \ldots$ are mutually disjoint

## Power set

Given $A$ the **power set** of $A$ denoted $P(A)$ is the set of all subsets of
$A$

example : The power set of $\{x, y\}$ is

$\{\emptyset, \{x\}, \{y\}, \{x, y\}\}$
