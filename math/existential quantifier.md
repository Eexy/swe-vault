---
id: existential quantifier
aliases: []
tags: []
---
# Existential quantifier


Let $Q(x)$ be a [[predicate]] and $D$ the domain of $x$. A **existential
statement** is a [[statement]] of the form $\exists x \in D, Q(x)$. It is
defined to be true if and only if $Q(x)$ is true for at least one $x$ in $D$.
It is defined to be false if and only if $Q(x)$ is false for every $x$ in $D$.

**example (true)** : $\exists x \in \mathbb{Z}$ such that $x^2 = 4$ — true because
$x = 2$ (or $x = -2$) satisfies this

**example (false)** : $\exists x \in \mathbb{Z}$ such that $x^2 = -1$ — false
because no integer squared gives a negative number

## Negation of an existential statement

The negation of an existential statement is logically equivalent to 

$$
\forall x \ in \ D, \neg Q(x)
$$

In other term the negation of an existential statement ("some are") is logically
equivalent to a universal statement ("none are" or "all are not")
