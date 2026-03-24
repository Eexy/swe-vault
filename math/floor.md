---
id: floor
aliases: []
tags: []
---
# Floor

Given any real number $x$, the **floor of** $x$, denoted $\lfloor x \rfloor$ is
defined as follows :

$\lfloor x \rfloor$ = that unique [[integer]] $n$ such that $n \leq x < n + 1$

Symbolically, if $x$ is a real number and $n$ is an integer, then 

$$
\lfloor x \rfloor = n
$$

## Theorem 1

For every real number $x$ and every integer $m$, $\lfloor x + m \rfloor = \lfloor x \rfloor + m$

**Proof.** Suppose anyr real number $x$ and any integer $m$ given

Let $n = \lfoor x \rfloor$. By definition of floor, $n$ is an integer and

$$
n \leq x < n + 1
$$

Add $m$ to all three parts to obtain 

$$
n + m \leq x + m < n + m + 1
$$

Now $n + m$ is an integer and so by definition of floor, the left-hand side of
the equation to be shown is

$$
\lfloor x + m \rfloor = n + m
$$

But $n = \lfoor x \rfloor$. Hence by subsitution

$$
n + m = \lfloor x \rfloor + m
$$
