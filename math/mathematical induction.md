---
id: mathematical induction
aliases: []
tags: []
---
# Mathematical induction

## Intuition — The Domino Analogy

Imagine an infinite line of dominoes, one behind the other. Suppose two things are true:

1. The **first** domino falls.
2. Whenever the **$k$th** domino falls, it knocks over the **$(k+1)$th** domino.

Then **all** dominoes fall. Mathematical induction works exactly the same way — if you can prove those two things about a property $P(n)$, the property holds for every integer from the starting point onward.

## Principle of Mathematical Induction

Let $P(n)$ be a property defined for [[integer|integers]] $n$, and let $a$ be a fixed integer. Suppose both of the following are true:

1. $P(a)$ is true
2. For every integer $k \ge a$, if $P(k)$ is true then $P(k+1)$ is true

Then the statement

$$\text{for every integer } n \ge a,\ P(n) \text{ is true}$$

is true.

> The validity of this principle is taken as an **axiom** — it is accepted on intuitive grounds and is equivalent to the *well-ordering principle* of the integers.
