---
id: summation notation
aliases: []
tags: []
---
# Summation notation

If $m$ and $n$ are [[integer]] and $m \le n$ the symbol $\sum_{k=m}^{n} = a_k$
read the summation from $k$ equals $m$ to $n$ of a sub k, is the sum of all the
[[sequence|terms]] $a_m + a_{m+1} + \ldots + a_n$

We say that's the **expended form** of the sum and we write

$$

\sum_{k=m}^{n} = a_m + a_{m+1} + \ldots + a_{n}
$$

We call $k$ the **index** of the summation $m$ the **lower limit** of the
summation and $n$ the **upper limit** of the summation

## Examples

### Using a single summation sign and separating off a final term

**a.** Write $\sum_{k=0}^{n} 2^k + 2^{n+1}$ as a single summation.

**b.** Rewrite $\sum_{i=1}^{n+1} \frac{1}{i^2}$ by separating off the final term.

**Solution**

**a.**

$$\sum_{k=0}^{n} 2^k + 2^{k+1} = (2^0 + 2^1 + 2^2 + \cdots + 2^n) + 2^{n+1} = \sum_{k=0}^{n+1} 2^k$$

**b.**

$$\sum_{i=1}^{n+1} \frac{1}{i^2} = \frac{1}{1^2} + \frac{1}{2^2} + \frac{1}{3^2} + \cdots + \frac{1}{n^2} + \frac{1}{(n+1)^2} = \sum_{i=1}^{n} \frac{1}{i^2} + \frac{1}{(n+1)^2}$$

### Telescoping sum

Some sums can be transformed so that successive cancellation of terms collapses the final result like a telescope. For instance, observe that for every integer $k \geq 1$:

$$\frac{1}{k} - \frac{1}{k+1} = \frac{(k+1) - k}{k(k+1)} = \frac{1}{k(k+1)}$$

Use this identity to find a simple expression for $\sum_{k=1}^{n} \frac{1}{k(k+1)}$.

**Solution**

$$\sum_{k=1}^{n} \frac{1}{k(k+1)} = \sum_{k=1}^{n} \left(\frac{1}{k} - \frac{1}{k+1}\right)$$

$$= \left(\frac{1}{1} - \frac{1}{2}\right) + \left(\frac{1}{2} - \frac{1}{3}\right) + \left(\frac{1}{3} - \frac{1}{4}\right) + \cdots + \left(\frac{1}{n} - \frac{1}{n+1}\right)$$

$$= 1 - \frac{1}{n+1}$$

### Transforming a sum by a change of variable

Transform $\displaystyle\sum_{k=0}^{6} \frac{1}{k+1}$ by making the change of variable $j = k + 1$.

**Solution**

First calculate the new limits:

- When $k = 0$, $j = k + 1 = 0 + 1 = 1$
- When $k = 6$, $j = k + 1 = 6 + 1 = 7$

Thus the new sum goes from $j = 1$ to $j = 7$. Next, replace each occurrence of $k$ by an expression in $j$. Since $j = k + 1$, then $k = j - 1$. Hence:

$$\frac{1}{k+1} = \frac{1}{(j-1)+1} = \frac{1}{j}$$

Putting the steps together:

$$\sum_{k=0}^{6} \frac{1}{k+1} = \sum_{j=1}^{7} \frac{1}{j}$$

Since $j$ is a dummy variable, it may be replaced by any other variable name. Substituting $k$ in place of $j$ gives $\displaystyle\sum_{j=1}^{7} \frac{1}{j} = \sum_{k=1}^{7} \frac{1}{k}$, and thus:

$$\sum_{k=0}^{6} \frac{1}{k+1} = \sum_{k=1}^{7} \frac{1}{k}$$

