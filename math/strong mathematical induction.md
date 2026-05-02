---
id: strong mathematical induction
aliases: []
tags: []
---
# Strong mathematical induction

A strong mathematical induction is similar to ordinary [[mathematical induction]] in
that it is a technique for establishing the truth of a [[sequence]] of [[statement]] about [[integer]]. 

Also a proof by strong mathematical induction consists of a basis step and an
inductive step.

However the basis step may contain proofs for several initial values and in the
inductive step the truth of a predicate $P(n)$ is assumed not just for one
values of $n$ but for all values through $k$ and then the truth of $P(k+1)$ is
proved

Here is the formal definition :

Let $P(n)$ be a property that is defined for integers $n$ and let $a$ and $b$ be
fixed integers with $a \le b$. Suppose the following two statement are true

1. $P(a)$, $P(a+1)$,...,$P(b)$ are all true (basis step)
2. For every integers $k \ge b$ if $P(i)$ is true for each integer $i$ from $a$ through $k$ then $P(k+1)$ is true (inductive step)

Then the following statement is true

$$
\text{for every integer } n \ge a, P(n)
$$

> [!note]
> Any statement that can be proved with ordinary mathematical induction can be
proved with strong mathematical induction. The reason is that given any integer
$k \ge b$ if the truth of $P(k)$ alone implies the truth of $P(k+1)$ then
certainly the truth of $P(a)$, $P(a+1)$,... and $P(k)$ implies the truth of
$P(k+1)$


> [!note]
> Any statement that can be proved strong mathematical induction can be proved
> with ordinary mathematical induction

## Example

**Theorem:** Any integer greater than 1 is divisible by a prime number.

**Proof (by strong mathematical induction):**

Let the property $P(n)$ be the sentence: $n$ is divisible by a prime number.

**Show that $P(2)$ is true:**

To establish $P(2)$, we must show that 2 is divisible by a prime number. This is true because 2 is divisible by 2 and 2 is a prime number.

**Show that for every integer $k \ge 2$, if $P(i)$ is true for each integer from 2 through $k$, then $P(k+1)$ is also true:**

Let $k$ be any integer with $k \ge 2$ and suppose that $i$ is divisible by a prime number for each integer $i$ from 2 through $k$ (inductive hypothesis). We must show that $k+1$ is divisible by a prime number.

**Case 1 ($k+1$ is prime):** In this case $k+1$ is divisible by a prime number, namely, itself.

**Case 2 ($k+1$ is not prime):** In this case $k+1 = ab$ where $a$ and $b$ are integers with $1 < a < k+1$ and $1 < b < k+1$. Thus, in particular, $2 \le a \le k$, and so by inductive hypothesis, $a$ is divisible by a prime number $p$. In addition because $k+1 = ab$, we have that $k+1$ is divisible by $a$. Hence, since $k+1$ is divisible by $a$ and $a$ is divisible by $p$, by transitivity of divisibility, $k+1$ is divisible by the prime number $p$.

Therefore, regardless of whether $k+1$ is prime or not, it is divisible by a prime number.

Since we have proved both the basis step and the inductive step of the strong mathematical induction, we conclude that the given statement is true. $\blacksquare$

