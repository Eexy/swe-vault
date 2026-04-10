---
id: product notation
aliases: []
tags: []
---
# Product notation

If $m$ and $n$ are [[integer|integers]] and $m \le n$, the symbol $\prod_{k=m}^{n} a_k$, read the **product from $k$ equals $m$ to $n$ of a-sub-$k$**, is the product of all the terms $a_m, a_{m+1}, a_{m+2}, \ldots, a_n$.

We write:

$$\prod_{k=m}^{n} a_k = a_m \cdot a_{m+1} \cdot a_{m+2} \cdots a_n$$

A recursive definition for the product notation is the following: if $m$ is any integer, then

$$\prod_{k=m}^{m} a_k = a_m \quad \text{and} \quad \prod_{k=m}^{n} a_k = \left(\prod_{k=m}^{n-1} a_k\right) \cdot a_n \quad \text{for every integer } n > m$$

