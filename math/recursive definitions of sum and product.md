---
id: recursive definitions of sum and product
aliases: []
tags: []
---
# Recursive definition of sum and product

Related: [[summation notation]] | [[product notation]]

## Definition

Given numbers $a_1, a_2, \ldots, a_n$, where $n$ is a positive integer, the **summation from $i = 1$ to $n$ of the $a_i$**, denoted $\sum_{i=1}^{n} a_i$, is defined as follows:

$$\sum_{i=1}^{1} a_i = a_1 \qquad \text{and} \qquad \sum_{i=1}^{n} a_i = \left(\sum_{i=1}^{n-1} a_i\right) + a_n, \quad \text{if } n > 1.$$

The **product from $i = 1$ to $n$ of the $a_i$**, denoted $\prod_{i=1}^{n} a_i$, is defined by:

$$\prod_{i=1}^{1} a_i = a_1 \qquad \text{and} \qquad \prod_{i=1}^{n} a_i = \left(\prod_{i=1}^{n-1} a_i\right) \cdot a_n, \quad \text{if } n > 1.$$

These definitions specify an *order* in which sums and products of more than two numbers are computed. For example:

$$\sum_{i=1}^{4} a_i = \left(\sum_{i=1}^{3} a_i\right) + a_4 = \left(\left(\sum_{i=1}^{2} a_i\right) + a_3\right) + a_4 = ((a_1 + a_2) + a_3) + a_4.$$

The recursive definitions are used with mathematical induction to establish various properties of general finite sums and products.

## Example 5.6.9 — A Sum of Sums

**Prove** that for any positive integer $n$, if $a_1, a_2, \ldots, a_n$ and $b_1, b_2, \ldots, b_n$ are real numbers, then:

$$\sum_{i=1}^{n} (a_i + b_i) = \sum_{i=1}^{n} a_i + \sum_{i=1}^{n} b_i.$$

**Proof** (by [[mathematical induction]]). Let the property $P(n)$ be the equation

$$\sum_{i=1}^{n} (a_i + b_i) = \sum_{i=1}^{n} a_i + \sum_{i=1}^{n} b_i. \tag{$P(n)$}$$

We must show that $P(n)$ is true for every integer $n \geq 1$.

**Show that $P(1)$ is true:** We must show that

$$\sum_{i=1}^{1} (a_i + b_i) = \sum_{i=1}^{1} a_i + \sum_{i=1}^{1} b_i.$$

Now $\sum_{i=1}^{1} (a_i + b_i) = a_1 + b_1 = \sum_{i=1}^{1} a_i + \sum_{i=1}^{1} b_i$ by definition of $\sum$. Hence $P(1)$ is true.

**Show that for every integer $k \geq 1$, if $P(k)$ is true then $P(k+1)$ is also true:** Suppose that $k$ is any integer with $k \geq 1$ and that $a_1, a_2, \ldots, a_k, a_{k+1}$ and $b_1, b_2, \ldots, b_k, b_{k+1}$ are real numbers such that

$$\sum_{i=1}^{k} (a_i + b_i) = \sum_{i=1}^{k} a_i + \sum_{i=1}^{k} b_i. \tag{inductive hypothesis}$$

We must show that

$$\sum_{i=1}^{k+1} (a_i + b_i) = \sum_{i=1}^{k+1} a_i + \sum_{i=1}^{k+1} b_i.$$

Now the left-hand side of the equation is:

$$\sum_{i=1}^{k+1} (a_i + b_i) = \sum_{i=1}^{k} (a_i + b_i) + (a_{k+1} + b_{k+1}) \tag{by definition of $\sum$}$$

$$= \left(\sum_{i=1}^{k} a_i + \sum_{i=1}^{k} b_i\right) + (a_{k+1} + b_{k+1}) \tag{by inductive hypothesis}$$

$$= \left(\sum_{i=1}^{k} a_i + a_{k+1}\right) + \left(\sum_{i=1}^{k} b_i + b_{k+1}\right) \tag{by associative and commutative laws}$$

$$= \sum_{i=1}^{k+1} a_i + \sum_{i=1}^{k+1} b_i \tag{by definition of $\sum$}$$

which equals the right-hand side of the equation. $\blacksquare$
