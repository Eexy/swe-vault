---
id: sequence
aliases: []
tags: []
---
# Sequence

A **sequence** is a [[function]] whose domain is either all the [[integer|integers]] between two
given integers or all the integers greater than or equal to a given integer

A sequence is typically represented as a [[set]] of elements written in a row.

$$
a_m, a_{m+1}, a_{m+1}, \ldots , a_n
$$

Each individual element $a_k$ is called a **term**. The $k$ is called a
**subscript** or **index**, $m$ is the subscript of the **initial term**, and
$n$ is the subscript of the **final term**

- $m$ : any integer
- $n$ : must be an integer that is greater than or equal to $m$

A sequence


$$
a_m, a_{m+1}, a_{m+1}, \ldots 
$$

denotes an **infinite sequence**. An **explicit formula** or **general formula**
for a sequence is a rule that shows how the values of $a_k$ depend on $k$

## Finding an explicit formula to fit given initial terms

Here is an example of how find the explicit formula with the initial terms of a sequence

**example**

Find an explicit formula for a sequence with the following initial terms:

$$1, -\frac{1}{4}, \frac{1}{9}, -\frac{1}{16}, \frac{1}{25}, -\frac{1}{36}, \ldots$$

**Solution** Denote the general term of the sequence by $a_k$ and suppose the first term is $a_1$. Note that the denominator of each term is a perfect square, so the terms can be rewritten as:

$$\frac{1}{1^2}, \frac{(-1)}{2^2}, \frac{1}{3^2}, \frac{(-1)}{4^2}, \frac{1}{5^2}, \frac{(-1)}{6^2}$$

The denominator of each term equals the square of the subscript of that term, and the numerator equals $\pm 1$. Hence:

$$a_k = \frac{\pm 1}{k^2}$$

The numerator oscillates between $+1$ and $-1$; it is $+1$ when $k$ is odd and $-1$ when $k$ is even. To achieve this oscillation, insert a factor of $(-1)^{k+1}$ into the formula for $a_k$. When $k$ is odd, $k+1$ is even and thus $(-1)^{k+1} = +1$; when $k$ is even, $k+1$ is odd and thus $(-1)^{k+1} = -1$. Consequently, an explicit formula that gives the correct first six terms is:

$$a_k = \frac{(-1)^{k+1}}{k^2} \quad \text{for every integer } k \geq 1$$

> [!note]
> Making the first term $a_0$ would lead to the alternative formula:
> $$a_k = \frac{(-1)^k}{(k+1)^2} \quad \text{for every integer } k \geq 0$$
