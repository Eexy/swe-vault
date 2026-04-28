---
id: geometric sequence
aliases: []
tags: []
---
# Geometric Sequence

A **geometric sequence** is a [[sequence]] where each term is obtained from the preceding one by multiplying by a constant factor called the **common ratio** $r$.

If the first term is $1$ and the common ratio is $r$, the sequence is:

$$1, r, r^2, r^3, \ldots, r^n, \ldots$$

## Sum of a Geometric Sequence

For every integer $n \ge 0$ and every real number $r \ne 1$, the sum of the first $n+1$ terms is:

$$\sum_{i=0}^{n} r^i = \frac{r^{n+1} - 1}{r - 1}$$

The expanded form is:

$$r^0 + r^1 + r^2 + \cdots + r^n = \frac{r^{n+1} - 1}{r - 1}$$

Because $r^0 = 1$ and $r^1 = r$, for $n \ge 1$ this can also be written as:

$$1 + r + r^2 + \cdots + r^n = \frac{r^{n+1} - 1}{r - 1}$$

> [!note]
> In discrete mathematics, $0^0 = 1$ by convention, so no special case is needed for $r = 0$.

## Proof

See [[proof by mathematical induction]] for a full proof of the sum formula using the basis step ($n = 0$) and inductive step ($n = k \Rightarrow n = k+1$).
