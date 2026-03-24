---
id: proof by contraposition
aliases: []
tags: []
---
# Proof by contraposition

The method of **proof by contraposition** is based on the [[logical equivalent|logical equivalence]]
between a [[statement]] and its 
[[conditional statement#contrapositive-of-a-conditional-statement|contrapositive]]

To prove a statement by a contraposition we take the contrapositive of the
statement, prove the contrapositive by a direct proof and conclude that original
statement is true

The underlying reasoning is that since a conditional statement is logically
equivalent to its contrapositive, if the contraspositive is true then the
statement must also be true

Here the the step to follow

1. express the statement to be proved in the form

$$
\forall x \text{in } D, \text{if } P(x) \text{then } Q(x)
$$

2. Rewrite this statement in the contrapositive form


$$
\forall x \text{in } D, \text{if } Q(x) \text{is false then }  P(x) \text{is false}
$$

3. Prove the contrapositive by a direct proof

**example**: For every [[integer]] $n$, if $n^2$ is even then $n$ is even

**Proof.** Suppose $n$ is any odd integer. By definition of odd $n = 2k+1$ for
some integer $k$. By substitution and algebra

$$
n^2 = (2k+1)^2 = 4k^2 + 4k + 1 = 2(2k^2 + 2k) + 1
$$

Now $2k^2 + 2k$ is an integer because products and sums of integers are
integers. So $n^2 = 2 \times (\text{an integer}) + 1$ and thus by definition of
odd $n^2$ is odd
