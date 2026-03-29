---
id: function
aliases: []
tags: []
---
# Function

A **function** $F$ from a [[set]] $A$ to a set $B$ is a
[[relation]] with domain $A$ and co-domain $B$ that satisfies the following two
properties

1. For every element $x$ in $A$, there is an element $y$ in $B$ such that 
    $(x,y) \in F$
2. For all elements $x$ in $A$ and $y$ and $z$ in $B$ we have :

$$
if \ (x,y) \in F \ and (x,z) \in F \ then y=z
$$

We can states thos 2 properties less formally as follows

1. every element of $A$ is the first element of an
    [[ordered tuple#ordered-pair|ordered pair]] of $F$
2. No two distinct ordered pair have the same first element

**example (function)** : $f: \mathbb{R} \to \mathbb{R}$ defined by $f(x) = x^2$.
Every real number has exactly one square, so both properties hold

**example (not a function)** : The "is parent of" relation from people to people
is not a function because one person can have multiple children — property 2 fails

## Equality of function

Two functions $f$ and $g$ are equal if and only if $f(x) = g(x)$ for all $x$ in
$A$

We write the equality of two functions like that :

$$
f = g
$$

**example** : $f(x) = (x+1)^2 - 2x - 1$ and $g(x) = x^2$ are equal functions because
expanding $f$ gives $x^2 + 2x + 1 - 2x - 1 = x^2 = g(x)$ for all $x$

