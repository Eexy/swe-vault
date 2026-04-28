---
id: proof by mathematical induction
aliases: []
tags: []
---
# Proof by mathematical induction

The method of [[proof]] by [[mathematical induction]] is used to prove a [[statement]] of the form:

> "For every integer $n \ge a$, a property $P(n)$ is true."

It consists of two steps:

**Step 1 — Basis step:** Show that $P(a)$ is true.

**Step 2 — Inductive step:** Show that for every integer $k \ge a$, if $P(k)$ is true then $P(k+1)$ is true.

To perform the inductive step:
- **Suppose** that $P(k)$ is true, where $k$ is any particular but arbitrarily chosen integer with $k \ge a$. *(This supposition is called the **inductive hypothesis**.)*
- **Show** that $P(k+1)$ is true.

## Example — Sum of a Geometric Sequence

See [[geometric sequence]] for the formula and context.

**Theorem:** For every integer $n \ge 0$ and every real number $r \ne 1$,

$$\sum_{i=0}^{n} r^i = \frac{r^{n+1} - 1}{r - 1}$$

**Proof (by mathematical induction):** Let $P(n)$ be the equation $\displaystyle\sum_{i=0}^{n} r^i = \frac{r^{n+1}-1}{r-1}$.

**Show that $P(0)$ is true:**

$$\sum_{i=0}^{0} r^i = r^0 = 1 \quad \text{and} \quad \frac{r^{0+1}-1}{r-1} = \frac{r-1}{r-1} = 1$$

Both sides are equal, so $P(0)$ is true.

**Show that for every integer $k \ge 0$, if $P(k)$ is true then $P(k+1)$ is also true:**

Suppose $k$ is any integer with $k \ge 0$ such that

$$\sum_{i=0}^{k} r^i = \frac{r^{k+1}-1}{r-1} \quad \leftarrow P(k) \text{ (inductive hypothesis)}$$

We must show that

$$\sum_{i=0}^{k+1} r^i = \frac{r^{k+2}-1}{r-1} \quad \leftarrow P(k+1)$$

The left-hand side of $P(k+1)$ is

$$\begin{align}
\sum_{i=0}^{k+1} r^i &= \sum_{i=0}^{k} r^i + r^{k+1} \\
&= \frac{r^{k+1}-1}{r-1} + r^{k+1} \quad \text{(by the inductive hypothesis)} \\
&= \frac{r^{k+1}-1}{r-1} + \frac{r^{k+1}(r-1)}{r-1} \\
&= \frac{r^{k+1}-1 + r^{k+2}-r^{k+1}}{r-1} \\
&= \frac{r^{k+2}-1}{r-1}
\end{align}$$

This equals the right-hand side of $P(k+1)$, so $P(k+1)$ is true.

Since both the basis step and the inductive step have been proved, the theorem is true.

---

## Example — Sum of the First $n$ Integers

**Theorem:** For every integer $n \ge 1$,

$$1 + 2 + \cdots + n = \frac{n(n+1)}{2}$$

**Proof (by mathematical induction):** Let $P(n)$ be the equation

$$1 + 2 + 3 + \cdots + n = \frac{n(n+1)}{2}$$

**Show that $P(1)$ is true:**

We must show that $1 = \frac{1(1+1)}{2}$. The right-hand side equals $\frac{2}{2} = 1$, which equals the left-hand side. Hence $P(1)$ is true.

**Show that for every integer $k \ge 1$, if $P(k)$ is true then $P(k+1)$ is also true:**

Suppose $k$ is any integer with $k \ge 1$ such that

$$1 + 2 + 3 + \cdots + k = \frac{k(k+1)}{2} \quad \leftarrow P(k) \text{ (inductive hypothesis)}$$

We must show that

$$1 + 2 + 3 + \cdots + (k+1) = \frac{(k+1)(k+2)}{2} \quad \leftarrow P(k+1)$$

The left-hand side of $P(k+1)$ is

$$\begin{align}
1 + 2 + 3 + \cdots + (k+1) &= 1 + 2 + 3 + \cdots + k + (k+1) \\
&= \frac{k(k+1)}{2} + (k+1) \quad \text{(by the inductive hypothesis)} \\
&= \frac{k(k+1)}{2} + \frac{2(k+1)}{2} \\
&= \frac{k^2+k}{2} + \frac{2k+2}{2} \\
&= \frac{k^2+3k+2}{2}
\end{align}$$

The right-hand side of $P(k+1)$ is

$$\frac{(k+1)(k+2)}{2} = \frac{k^2+3k+2}{2}$$

Both sides are equal, so $P(k+1)$ is true.

Since both the basis step and the inductive step have been proved, the theorem is true.
