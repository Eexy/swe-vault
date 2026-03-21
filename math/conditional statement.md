---
id: conditional statement
aliases: []
tags: []
---
# Conditional statement

If $p$ and $q$ are sttatement variables a **conditional statement** is a
[[statement]] with the form "if $p$ then $q$" or "$p$ implies $q$" and is
denoted $p \implies q$

A conditional statement is false when $p$ is true and $q$ is false, otherwise it
is true

**example** : "If it rains then the ground is wet"
- It rains and the ground is wet → true
- It rains but the ground is not wet → false (broken promise)
- It does not rain but the ground is wet (from a hose) → true (the promise was never broken)

In a conditional statement $p$ is called the **hypothesis** or the **antecedent** and
$q$ the **conclusion** or the **consequent**

Here is the [[truth table]]

| P | Q | P → Q |
|-|-|-----|
| V | V |   V   |
| V | F |   F   |
| F | V |   V   |
| F | F |   V   |

A conditional statement that is true by virtue of the fact that its hypothesis
is false is often called **vacuously true** or **true by default**

**example** : "If 2 is odd then the moon is made of cheese" — the hypothesis "2 is
odd" is false, so the whole statement is vacuously true

## Representation of a conditional statement as OR

A conditional statement can also be represented a an disjunction statement

$$
p \implies q \equiv \neg p \lor q
$$

## Negation of a conditional statement

The negation of a conditional statement is

$$
\neg (p \implies q) \equiv p land \neg q
$$

## Contrapositive of a conditional statement

The **contrapositive** of a conditional statement of the form "if $p$ then $q$"
is

$$
If \ \neg q \ then \neg p
$$

A conditional statement is always [[logical equivalent|logically equivalent]] to
its contrapositive

**example** : "If it rains then the ground is wet" has the contrapositive "If the
ground is not wet then it did not rain" — both say the same thing

## Converse and inverse of a conditional statement

The converse and the inverse of a conditional statement are
[[logical equivalent|logically equivalent]] to each other

### Converse of a conditional statement

The **converse** of a conditional statement is :

$$
q \implies p
$$

**example** : The converse of "If it rains then the ground is wet" is "If the
ground is wet then it rains" — this is NOT equivalent (a hose could wet the ground)

### Inverse of a conditional statement

The **inverse** of a conditional statement is :

$$
\neg p \implies \neg q
$$

**example** : The inverse of "If it rains then the ground is wet" is "If it does
not rain then the ground is not wet" — also not equivalent for the same reason

## Biconditional statement

The **biconditional statement** of two variable $p$ and $q$ is "p if, and only
if q" is denoted as $p \iff q $

A biconditional statement is true if both $p$ and $q$ have the same truth values
and is false if $p$ and $q$ have opposite truth values

**example** : "An integer $n$ is even if and only if $n$ is divisible by 2" — both
directions hold: even implies divisible by 2, and divisible by 2 implies even

| P | Q | P ↔ Q |
|:-:|:-:|:-----:|
| V | V |   V   |
| V | F |   F   |
| F | V |   F   |
| F | F |   V   |

## Necessary and sufficient condition

If $r$ and $s$ aare [[statement]] we say that

- $r$ is a **sufficient condition** for $s$ which means than "if r then s"
- $r$ is a **necessary condition** for $s$ which means than "if not r then not s"

In a sufficient condition $s$ is true the moment of $r$ is also true even if
other statement variable are not. So we have "if s then r"

In a necessay condition $s$ is true if $r$ is true. If $r$ is false then $s$ is
also false even if other statement variable are true so we can sy that 
"r if, and only if, s"


