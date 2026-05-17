---
id: fibonnaci sequence
aliases: []
tags: []
---
# Fibonacci Sequence

The **Fibonacci sequence** is a [[sequence]] defined by the initial conditions

$$
F_0 = 1, \quad F_1 = 1
$$

and the [[recurrence relation]]

$$
F_k = F_{k-1} + F_{k-2} \text{ for every integer } k \ge 2
$$

The first several terms are:

$$
1, 1, 2, 3, 5, 8, 13, 21, 34, 55, \ldots
$$

## As a Second Order Linear Homogenous Recurrence Relation

The Fibonacci sequence is an example of a [[second order linear homogenous recurrence relation with constant coefficients]] with $A = 1$ and $B = 1$:

$$
F_k = 1 \cdot F_{k-1} + 1 \cdot F_{k-2}
$$

## Closed-Form Formula

The $n$-th Fibonacci number can be expressed via an [[sequence|explicit formula]]

$$
F_n = \frac{1}{\sqrt{5}}\left(\frac{1+\sqrt{5}}{2}\right)^{n+1} - \frac{1}{\sqrt{5}}\left(\frac{1-\sqrt{5}}{2}\right)^{n+1}
$$

where $\dfrac{1+\sqrt{5}}{2}$ (the **golden ratio**) and $\dfrac{1-\sqrt{5}}{2}$ are the roots of the characteristic equation $t^2 - t - 1 = 0$.

> [!note]
> Although $F_n$ is expressed using irrational numbers, the result is always a positive integer because the irrational parts cancel exactly.
