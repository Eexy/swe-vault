---
id: divisibility
aliases: []
tags: []
---
# Divisibility

If $n$ and $d$ are [[integer]] then :

n is **divisible by** d if and only if $n$ equals $d$ times some integer and $d \neq 0$ 

Instead of "n is divisible by d" we can say that

1. $n$ is a multiple of $d$
2. $d$ is a factor $n$
3. $d$ is a divisor of $n$
4. $d$ divides $n$

The notation $d|n$ is read $d$ divides $n$

$$
d|n \Leftrightarrow \exists \ an \ integer \ say \ k \ such \ that \ n = dk \ and \ d \neq 0
$$

**examples** :
- $3 \mid 12$ because $12 = 3 \times 4$
- $7 \mid 35$ because $35 = 7 \times 5$
- $4 \nmid 10$ because there is no integer $k$ such that $10 = 4k$

## Transitivity of divisibility

For all integers $a$, $b$ and $c$, if $a$ divides $b$ and $b$ divides $c$ then
$a$ divides $c$

**example** : $3 \mid 6$ and $6 \mid 24$, therefore $3 \mid 24$ (since $24 = 3 \times 8$)

**Proof.** Suppose $a$, $b$, and $c$ are particular but arbitrarily chosen integers
such that $a \mid b$ and $b \mid c$. We must show that $a \mid c$.

By definition of divisibility:

$$
b = a \cdot r \quad \text{for some integer } r
$$
$$
c = b \cdot s \quad \text{for some integer } s
$$

Substituting the first equation into the second:

$$
c = (a \cdot r) \cdot s = a \cdot (rs)
$$

Since $r$ and $s$ are integers, $rs$ is an integer. Therefore $c = a \cdot (rs)$
satisfies the definition of divisibility, so $a \mid c$. $\blacksquare$

## Divisibility by a prime

Any integer $n > 1$ is divisible by a prime number

**examples** :
- $12$ is divisible by $2$ (prime)
- $15$ is divisible by $3$ (prime)
- $7$ is divisible by $7$ itself (prime)

**Proof.** Suppose $n$ is a particular but arbitrarily chosen integer greater than 1 

We must show that there is a prime number that divides $n$.

If $n$ is prime, then $n$ is divisible by a prime number (namely itself), and we
are done.

If $n$ is not prime, then $n = r_0 s_0$ where $r_0$ and $s_0$ are integers with
$1 < r_0 < n$ and $1 < s_0 < n$. By definition of divisibility, $r_0 \mid n$.

If $r_0$ is prime, then $r_0$ is a prime number that divides $n$, and we are
done. If $r_0$ is not prime, then $r_0 = r_1 s_1$ where $1 < r_1 < r_0$ and
$1 < s_1 < r_0$. By definition of divisibility $r_1 \mid r_0$, and since
$r_0 \mid n$, by transitivity of divisibility $r_1 \mid n$.

We may continue this process, factoring successive factors of $n$ into smaller
and smaller pieces. We must succeed in a finite number of steps because each new
factor is both less than the previous one and greater than 1, and there are
finitely many integers strictly between 1 and $n$. This produces a sequence

$$
r_0,\ r_1,\ r_2,\ \ldots,\ r_k
$$

where $k \geq 0$, $1 < r_k < r_{k-1} < \cdots < r_1 < r_0 < n$, and $r_i \mid n$
for each $i = 0, 1, \ldots, k$. The process terminates when $r_k$ is prime.
Hence $r_k$ is a prime number that divides $n$. $\blacksquare$

