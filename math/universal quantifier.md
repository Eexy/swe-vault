---
id: universal quantifier
aliases: []
tags: []
---
# Universal quantifier

Let $Q(x)$ be a [[predicate]] and $D$ the domain of $x$. A **universal
statement** is a [[statement]] of the form $\forall x \in D, Q(x)$. It is
defined to be true if and only if $Q(x)$ is true for each individual $x$ in $D$.
It is defined to be false if and only if $Q(x)$ is false for at least one $x$ in
$D$. A value for $x$ for which $Q(x)$ is false is called a **counterexample** to
the universal statement

**example** : $\forall x \in \mathbb{Z}$, if $x$ is even then $x^2$ is even — true
for all integers

**example of a counterexample** : The statement "all primes are odd" is false.
The counterexample is $x = 2$: it is prime but even

## Proving a universal statement with exhaustion

One way to prove a universal statement is to use **exhaustion**. With this
method we prove that the statement is true for each individual element of the
domain

This method is applicable only when the domain is finite

## Negation of a universal statement

The negation of a universal statement is logically equivalent to 

$$
\exists x \ in \ D \ such \ that \neg Q(x)
$$

In other terms the negation of a universal statement ("all are") is logically
equivalent to an existential statement ("some are" or "there is at least one that
is not")

## Universal conditional statement

For the next example we will use the universal conditional statement

$$
\forall x, \ if P(x) \ then \ Q(x)
$$

### Negation of a universal conditional statement


The negation of an universal conditional statement is

$$
\neg (\forall x, \ if P(x) \ then \ Q(x)) \equiv \exists x \ such \ that P(x) \ and \neg Q(x)
$$

### Contrapositive of an universal conditional statement

The [[conditional statement#conditional-statement#contrapositive-of-a-conditional-statement|contrapositive of a universal conditional statement]]
is :

$$
\forall x \in D \ if \neg Q(x) \ then \neg P(x)
$$

### Converse of an universal conditional statement

The [[conditional statement#conditional-statement#converse-and-inverse-of-a-conditional-statement|converse of a universal conditional statement]]
is :

$$
\forall x \in D \ if Q(x) \ then P(x)
$$


### Inverse of an universal conditional statement

The [[conditional statement#conditional-statement#converse-and-inverse-of-a-conditional-statement|inverse of an universal conditional statement]]
is :

$$
\forall x \in D \ if \neg P(x) \ then \neg Q(x)
$$




