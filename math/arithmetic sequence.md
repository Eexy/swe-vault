---
id: arithmetic sequence
aliases: []
tags: []
---
# Arithmetic sequence

A [[sequence]] $a_1, a_2, a_3, \cdots$ is called an **arithmetic sequence** if,
and onlyy if there is a constant $d$ such that

$$
a_k = a_{k-1} + d \text{ for each integer } k \ge 1
$$

it follows that 

$$
a_n = a_0 + dn
$$

## Sum of an Arithmetic Sequence

For every integer $n \ge 0$, the sum of the first $n+1$ terms of an arithmetic sequence starting at $a_0$ with common difference $d$ is:

$$\sum_{k=0}^{n} (a_0 + dk) = (n+1)a_0 + d\frac{n(n+1)}{2}$$

The expanded form is:

$$a_0 + (a_0 + d) + (a_0 + 2d) + \cdots + (a_0 + nd) = (n+1)a_0 + d\frac{n(n+1)}{2}$$

This can also be written in terms of the first and last terms $a_0$ and $a_n = a_0 + dn$:

$$\sum_{k=0}^{n} a_k = \frac{(n+1)(a_0 + a_n)}{2}$$
