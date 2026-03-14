---
id: De Margan's law
aliases: []
tags: []
---
# De Morgan's Law

The **De Morgan's law** tell us that :

1. the negation of an $and$ [[statement]]is [[logical equivalent|logically equivalent]] to
the $or$ statement in which each component is negated
2. the negation of an $or$ [[statement]]is [[logical equivalent|logically equivalent]] to
the $and$ statement in which each component is negated

**example** :

### example 1: Negation of a Conjunction
**¬(p ∧ q) ≡ ¬p ∨ ¬q**

> *"It is not the case that it is both raining AND cold"*
> *is equivalent to*
> *"It is not raining OR it is not cold"*

| p (raining) | q (cold) | p ∧ q | ¬(p ∧ q) | ¬p | ¬q | ¬p ∨ ¬q |
|-------------|----------|-------|----------|----|----|---------|
| T | T | T | F | F | F | F |
| T | F | F | T | F | T | T |
| F | T | F | T | T | F | T |
| F | F | F | T | T | T | T |

Columns **¬(p ∧ q)** and **¬p ∨ ¬q** are identical → Logically equivalent.

---

### example 2: Negation of a Disjunction
**¬(p ∨ q) ≡ ¬p ∧ ¬q**

> *"It is not the case that she is at the gym OR at the library"*
> *is equivalent to*
> *"She is not at the gym AND she is not at the library"*

| p (at gym) | q (at library) | p ∨ q | ¬(p ∨ q) | ¬p | ¬q | ¬p ∧ ¬q |
|------------|----------------|-------|----------|----|----|---------|
| T | T | T | F | F | F | F |
| T | F | T | F | F | T | F |
| F | T | T | F | T | F | F |
| F | F | F | T | T | T | T |

Columns **¬(p ∨ q)** and **¬p ∧ ¬q** are identical → Logically equivalent.
