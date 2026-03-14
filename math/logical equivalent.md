---
id: logical equivalent
aliases: []
tags: []
---
# Logical equivalence

Two [[statement form]] are called **logically equivalent** if and only if they have
identical truth values for each possible substitution of statements for their
statement variables. The logical equivalence of statement form $P$ and $Q$ is
denoted by writting $P \equiv Q$

We can also says that two statements are called **logically equivalent** if and
only if they have logically equivalent forms when identical component statement
variables are used to replace identical component statements

**example** 

We'll prove that **¬(p ∧ q) ≡ ¬p ∨ ¬q**

| p | q | p ∧ q | ¬(p ∧ q) | ¬p | ¬q | ¬p ∨ ¬q |
|---|---|-------|----------|----|----|---------|
| T | T | T | F | F | F | F |
| T | F | F | T | F | T | T |
| F | T | F | T | T | F | T |
| F | F | F | T | T | T | T |

Since the columns for **¬(p ∧ q)** and **¬p ∨ ¬q** are identical, the two expressions are logically equivalent.

