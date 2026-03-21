---
id: direct proof
aliases: []
tags: []
---
# Direct proof

## Proving existential statements

If we have a [[statement]] in the form

$$
\exists x \in D \ such \ that Q(x)

$$

we now that this statement is only true if there is at least one $x$ in $D$ for
which the [[predicate]] $Q$ is true

So to prove an existential statement we only have to find $x$ where $Q(x)$ is
true

## Disproving an existential statement is false

[[existential quantifier#negation-of-an-existential-statement|The negation of an existential statement]] is a universal statement.
So to disprove a existential statement we must prive the universal statement

## Disproving an universal statement by couterexample

To disprove a [[universal quantifier|universal statement]] with the form

$$
\forall x \in D, \ if P(x) \ then \ Q(x)
$$

We only have to find one $x$ in $D$ where $P(x)$ is true but $Q(x)$ is false. We say that we use
a **counterexample**

## Proving universal statements

To prove a [[universal quantifier|universal statement]] we have two possible
ways

### Method of exhaustion

If $D$ in the statement is finite we can use the method of exhaustion. In this
case we will test all $x$ individually to see if the statement is true

### Generalizing from the Generic Particular

One way to prove a universal statement is to generalize the proof following
those steps

1. Express the statement to be proved in the form "For every $x \in D$, if $P(x)$ then $Q(x)$"
2. Start the proof by supposing $x$ is a particular but arbitrarily chosen
   element of $D$ for which $P(x)$ is true (this step is often abbreviated "Suppose $x \in D$ and $P(x)$")
3. Show that the conclusion $Q(x)$ is true by using definitions, previously
   established results, and the rules for logical inference

**example** : Prove that for all integers $n$, if $n$ is [[even number|even]] then $n^2$ is even

*Proof.* Suppose $n$ is a particular but arbitrarily chosen even integer. By
definition of [[even number]], $n = 2k$ for some integer $k$. Then

$$
n^2 = (2k)^2 = 4k^2 = 2(2k^2)
$$

Since $2k^2$ is an integer, $n^2 = 2 \times (2k^2)$ satisfies the definition of
even. Therefore $n^2$ is even. $\blacksquare$


