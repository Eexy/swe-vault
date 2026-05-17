---
id: second order linear homogenous recurrence relation with constant coefficients
aliases: []
tags: []
---
# Second order linear homogenous recurrence relation with constant coefficients

A **second order linear homogenous recurrence relation with constant coefficients** is a [[recurrence relation]] of the form

$$
a_{k} = Aa_{k-1} + Ba_{k-2} \text{ for every integer } k \ge \text{ some fixed integer}
$$

Where $A$ and $B$ are fixed real numbers with $B \neq 0$

"Second order" refers to the fact that the expression for $a_k$ contains the two
previous terms $a_{k-1}$ and $a_{k-2}$, "linear" to the fact that $a_{k-1}$ and $a_{k-2}$ appear in separate terms and to the first power

"homogenous" refers to the fact that the total degree of each term is the same
(thus there is no constant term) and "constant coefficients" to the fact that $A$ and $B$ are fixed real numbers that do not depend on $k$

An example of second order linear homogenous recurrence relation with constant
coefficients is the [[fibonnaci sequence]]

## Characteristic equation of the relation

Given a second order linear homogenous recurrence relation with constant coefficients 

$$
a_{k} = Aa_{k-1} + Ba_{k-2} \text{ for every integer } k \ge \text{ some fixed integer}
$$

the **characteristic equation of the relation** is

$$
t^2-At-B = 0
$$

The characteristic equation give us an [[sequence|explicit formula]] to compute
$a_k$

The logic behind it is the following :

The relation is satisfied when each $a_i = 0$, but it has nonzero solutions as well. Suppose that for some number $t$ with $t \neq 0$, the sequence $1, t, t^2, t^3, \ldots, t^n, \ldots$ satisfies the relation. This means that each term equals $A$ times the previous term plus $B$ times the term before that. So for each integer $k \ge 2$:

$$
t^k = At^{k-1} + Bt^{k-2}
$$

In particular, when $k = 2$, the equation becomes $t^2 = At + B$, or equivalently:

$$
t^2 - At - B = 0
$$

This is a quadratic equation, and the values of $t$ that make it true can be found either by factoring or by using the quadratic formula.

Now work backward. Suppose $t$ is any number that satisfies $t^2 - At - B = 0$. Multiplying by $t^{k-2}$:

$$
t^{k-2} \cdot t^2 - t^{k-2} \cdot At - t^{k-2} \cdot B = 0
$$

This is equivalent to

$$
t^k - At^{k-1} - Bt^{k-2} = 0
$$

or

$$
t^k = At^{k-1} + Bt^{k-2}
$$

Hence $1, t, t^2, t^3, \ldots, t^n, \ldots$ satisfies the relation.

### Using the characteristic equation to find solutions to a recurrence relation

Consider the recurrence relation that specifies that the $k$th term of a sequence equals the sum of the $(k-1)$st term plus twice the $(k-2)$nd term. That is,

$$
a_k = a_{k-1} + 2a_{k-2} \text{ for each integer } k \ge 2
$$

Find all sequences that satisfy this relation and have the form $1, t, t^2, t^3, \ldots, t^n, \ldots$ where $t$ is nonzero.

The sequence $1, t, t^2, t^3, \ldots, t^n, \ldots$ satisfies the relation if, and only if, $t$ satisfies the characteristic equation:

$$
t^2 - t - 2 = 0
$$

Since $t^2 - t - 2 = (t-2)(t+1)$, the only possible values of $t$ are $2$ and $-1$. It follows that the sequences

$$
1, 2, 2^2, 2^3, \ldots, 2^n, \ldots \quad \text{and} \quad 1, -1, (-1)^2, (-1)^3, \ldots, (-1)^n, \ldots
$$

are both solutions and there are no other solutions of this form. These sequences can be rewritten more simply as

$$
1, 2, 4, 8, \ldots, 2^n, \ldots \quad \text{and} \quad 1, -1, 1, -1, \ldots, (-1)^n, \ldots
$$

This shows how to find two distinct sequences that satisfy a given second-order linear homogeneous recurrence relation with constant coefficients. Any linear combination of such sequences produces another sequence that also satisfies the relation.

### Finding the linear combination that satisfies the initial conditions

We can use the characteristic equation to find an explicit formula for a
relation with initial condition. There is two case.

1. Multiple roots
2. One root

#### Distinct-Roots theorem

**Distinct-Roots Theorem** — Suppose a sequence $a_0, a_1, a_2, \ldots$ satisfies a recurrence relation

$$
a_k = Aa_{k-1} + Ba_{k-2}
$$

for some real numbers $A$ and $B$ with $B \neq 0$ and every integer $k \ge 2$. If the characteristic equation $t^2 - At - B = 0$ has two distinct roots $r$ and $s$, then $a_0, a_1, a_2, \ldots$ is given by the explicit formula

$$
a_n = Cr^n + Ds^n
$$

where $C$ and $D$ are the numbers whose values are determined by the values of $a_0$ and $a_1$. That is, $C$ and $D$ are the solutions to the system:

$$
a_0 = C + D \quad \text{and} \quad a_1 = Cr + Ds
$$

For example :

Find a sequence that satisfies the recurrence relation

$$
a_k = a_{k-1} + 2a_{k-2} \text{ for every integer } k \ge 2
$$

and that also satisfies the initial conditions $a_0 = 1$ and $a_1 = 8$.

From the previous example, the two sequences $1, 2, 2^2, 2^3, \ldots$ and $1, -1, 1, -1, \ldots$ both satisfy the relation. Neither satisfies the given initial conditions, but any sequence $a_0, a_1, a_2, \ldots$ that satisfies the explicit formula

$$
a_n = C \cdot 2^n + D(-1)^n
$$

where $C$ and $D$ are numbers, also satisfies the relation. We find $C$ and $D$ by substituting $n = 0$ and $n = 1$:

$$
a_0 = 1 = C \cdot 2^0 + D(-1)^0
$$

$$
a_1 = 8 = C \cdot 2^1 + D(-1)^1
$$

Simplifying gives the system:

$$
1 = C + D
$$

$$
8 = 2C - D
$$

Adding the two equations gives $9 = 3C$, so $C = 3$. Substituting into $1 = C + D$ gives $D = -2$.

It follows that the sequence $a_0, a_1, a_2, \ldots$ given by

$$
a_n = 3 \cdot 2^n + (-2)(-1)^n = 3 \cdot 2^n - 2(-1)^n
$$

for each integer $n \ge 0$, satisfies both the recurrence relation and the given initial conditions.

##### Find an explicit formula for the Fibonacci sequence

The [[fibonnaci sequence]] $F_0, F_1, F_2, \ldots$ satisfies the recurrence relation

$$
F_k = F_{k-1} + F_{k-2} \text{ for every integer } k \ge 2
$$

with initial conditions $F_0 = F_1 = 1$. The Fibonacci sequence satisfies the hypothesis of the distinct-roots theorem since it is a second-order linear homogeneous recurrence relation with constant coefficients ($A = 1$ and $B = 1$). The characteristic equation is:

$$
t^2 - t - 1 = 0
$$

By the quadratic formula:

$$
t = \frac{1 \pm \sqrt{1 - 4(-1)}}{2} = \begin{cases} \dfrac{1 + \sqrt{5}}{2} \\[6pt] \dfrac{1 - \sqrt{5}}{2} \end{cases}
$$

The roots are distinct, so by the distinct-roots theorem the Fibonacci sequence is given by

$$
F_n = C\left(\frac{1+\sqrt{5}}{2}\right)^n + D\left(\frac{1-\sqrt{5}}{2}\right)^n \text{ for each integer } n \ge 0
$$

where $C$ and $D$ are determined by $F_0 = F_1 = 1$. Substituting $n = 0$ and $n = 1$:

$$
F_0 = 1 = C + D
$$

$$
F_1 = 1 = C\left(\frac{1+\sqrt{5}}{2}\right) + D\left(\frac{1-\sqrt{5}}{2}\right)
$$

Solving the system gives:

$$
C = \frac{1+\sqrt{5}}{2\sqrt{5}} \quad \text{and} \quad D = \frac{-(1-\sqrt{5})}{2\sqrt{5}}
$$

Substituting back into the formula and simplifying:

$$
F_n = \frac{1}{\sqrt{5}}\left(\frac{1+\sqrt{5}}{2}\right)^{n+1} - \frac{1}{\sqrt{5}}\left(\frac{1-\sqrt{5}}{2}\right)^{n+1}
$$

for each integer $n \ge 0$. Remarkably, even though the formula involves $\sqrt{5}$, all of the values of the Fibonacci sequence are integers.

#### Single-Root Theorem

**Single-Root Theorem** — Suppose a sequence $a_0, a_1, a_2, \ldots$ satisfies a recurrence relation

$$
a_k = Aa_{k-1} + Ba_{k-2}
$$

for some real numbers $A$ and $B$ with $B \neq 0$ and every integer $k \ge 2$. If the characteristic equation $t^2 - At - B = 0$ has a single (real) root $r$, then $a_0, a_1, a_2, \ldots$ is given by the explicit formula

$$
a_n = Cr^n + Dnr^n
$$

where $C$ and $D$ are the real numbers whose values are determined by the values of $a_0$ and any other known value of the sequence.

##### Example

Suppose a sequence $b_0, b_1, b_2, \ldots$ satisfies the recurrence relation

$$
b_k = 4b_{k-1} - 4b_{k-2} \text{ for every integer } k \ge 2
$$

with initial conditions $b_0 = 1$ and $b_1 = 3$. Find an explicit formula for $b_0, b_1, b_2, \ldots$

This sequence satisfies the single-root theorem since it is a second-order linear homogeneous recurrence relation with constant coefficients ($A = 4$ and $B = -4$). The characteristic equation

$$
t^2 - 4t + 4 = 0
$$

has the unique root $r = 2$ since $t^2 - 4t + 4 = (t-2)^2$. By the single-root theorem, $b_0, b_1, b_2, \ldots$ is given by

$$
b_n = C \cdot 2^n + Dn \cdot 2^n \text{ for each integer } n \ge 0
$$

where $C$ and $D$ are determined by $b_0 = 1$ and $b_1 = 3$. Substituting:

$$
b_0 = 1 = C \cdot 2^0 + D \cdot 0 \cdot 2^0 = C
$$

$$
b_1 = 3 = C \cdot 2^1 + D \cdot 1 \cdot 2^1 = 2C + 2D
$$

From the first equation $C = 1$. Substituting into the second: $2 + 2D = 3$, so $D = \dfrac{1}{2}$.

It follows that

$$
b_n = 2^n + \frac{1}{2} \cdot n \cdot 2^n = 2^n\left(1 + \frac{n}{2}\right) \text{ for each integer } n \ge 0
$$

