---
id: function
aliases: []
tags: []
---
# Function

A **function** $F$ from a [[set]] $A$ to a set $B$ is a [[relation]] with domain $A$ and co-domain $B$ that satisfies the following two properties

1. For every element $x$ in $A$, there is an element $y$ in $B$ such that 
    $(x,y) \in F$
2. For all elements $x$ in $A$ and $y$ and $z$ in $B$ we have :

$$
if \ (x,y) \in F \ and (x,z) \in F \ then y=z
$$

We can states those 2 properties less formally as follows

1. every element of $A$ is the first element of an
    [[ordered tuple#ordered-pair|ordered pair]] of $F$
2. No two distinct ordered pair have the same first element

**example (function)** : $f: \mathbb{R} \to \mathbb{R}$ defined by $f(x) = x^2$.
Every real number has exactly one square, so both properties hold

**example (not a function)** : The "is parent of" relation from people to people
is not a function because one person can have multiple children — property 2 fails

## Equality of function

Two functions $F : X \rightarrow Y$ and $G : X \rightarrow Y$ are equal if and only if $F(x) = G(x)$ for all $x$ in $X$

We write the equality of two functions like that :

$$
F = G
$$

**example** : $f(x) = (x+1)^2 - 2x - 1$ and $g(x) = x^2$ are equal functions because
expanding $f$ gives $x^2 + 2x + 1 - 2x - 1 = x^2 = g(x)$ for all $x$

## Image, Inverse and Range of a function

Given a function $f$ from a [[set]] $X$ to a set $Y$, denoted $f : X \rightarrow Y$ where $X$ is the domain and $Y$ the co-domain. Given that for any element $x$ in $X$ there is a unique related element $y$ in $Y$. We can denote $y$ as $f(x)$

- $f(x)$ is called the **image** of $x$ under $f$
- any $x$ with $f(x) = y$ is called a **preimage** (inverse image) of $y$

The **inverse image** of $y$ is the set of all such preimages: $$f^{-1}(y) = \{x \in X \mid f(x) = y\}$$
The set of all **images** is called the range of the function it corresponds to

$$
\text{range of f} = \{y \in Y |y = f(x) \}
$$
## Well defined function

A function is **well defined** if it satisfy those two properties

1. There must be exactly one unique element $y$ associated to $x$
2. Each $x$ must be associated to an $y$

**Example** Here is a function $f$ define like that : f(x) is the real number $y$ such that $x^2 + y^2 = 1$

## Injective (one-to-one function)

Let $F$ be a function from a set $X$ to a set $Y$. $F$ is **one-to-one** or **injective** if and only if for all elements $z_1$ and $x_2$ in $X$

- if $F(x_1) = F(x_2)$ then $x_1 = x_2$
- if $x_1 \neq x_2$ then $F(x_1) \neq F(x_2)$

That definition means that a injective function each element of the co-domain is the image of at most one element of the domain

The best way to prove that a function is injective or not is to use [[direct proof]]

## Surjective (onto function)

Let $F$ be a function from a set $X$ to a set $Y$. $F$ is **surjective** or **onto** if and only if given any element $y$ in $Y$. It is possible to find an element $x$ in $X$ with the property  that $y = F(x)$

symbolically that means

$$
F : X \rightarrow Y \text{ is onto } \leftrightarrow \forall y \in Y, \exists x \in X \text{ such that } F(x) = y
$$

In other word a surjective function is a function where every image has a pre image. When a function is a surjective function then its range is equal to its co-domain

The best way to prove that a function is surjective is to use [[direct proof#Generalizing from the Generic Particular|generalizaiton]]

## Bijection

A **one-to-one correspondence** or **bijonction** from a set $X$ to a set $Y$ is a function $F : X \rightarrow Y$ that is both one-to-one (injective) and onto (surjective)

## Inverse function

Suppose $F : X \rightarrow Y$ is a one-to-one correspondence (bijection), in other words, suppose $F$ is one-to-one and onto. Then there is a function $F^{-1} : Y \rightarrow X$ that is defined as follows :

Given any element $y$ in $Y$

$$
F^{-1}(y) = \text{ that unique element } x \in X \text{ such that } F(x) \text { equal } y
$$

This function is called the **inverse function**

## Composition of function

Let $f : X \rightarrow Y$ and $g : Y' \rightarrow Z$ be functions with the property that the range of $f$ is a [[subset]] of the domain of $g$. Define a new function $g \circ f : X \rightarrow Z$ as follows :

$$
(g \circ f)(x) = g(f(x)) \text{ for each } x \in X
$$
where $g \circ f$ is read "g circle f" and $g(f(x))$ is read "g of f of $x$" The function $g \circ f$ is called the **composition of $f$ and $g$**

Here is the visual representation :

![[function_composition.png]]

### Composition of function with its inverse

If $f : X \rightarrow Y$ is a one-to-one and onto function with inverse function $f^{-1} : Y \rightarrow X$ then we have

$$
f^{-1} \circ f = I_x 
$$

and 



$$
f \circ f ^{-1}  = I_x 
$$

where $I_x$ is the [[identity function]]

### Composition of one-to-one function

if $f : X \rightarrow Y$ and $g : Y \rightarrow Z$ are both one-to-one functions then $g \circ f$ is one-to-one

Here is how to prove it

![[proof_composition_one_to_one.png]]

![[proof_composition_one_to_one_part_2.png]]

### Composition of onto function

if $f : X \rightarrow Y$ and $g : Y \rightarrow Z$ are both one-to-one functions then $g \circ f$ is onto

Here is how to prove it

![[proof_composition_onto.png]]

![[proof_composition_onto_part_2.png]]