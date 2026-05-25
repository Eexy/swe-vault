---
id: set equality
aliases: []
tags: []
---
# Set equality

Two [[set]] $A$ an $B$ are equal if and only if they have exactly the same elements

We can use this formal definition using the language of [[subset]] :

Given sets $A$ and $B$, $A$ **equal** $B$, written $A = B$, if and only if
every element of $A$ is in $B$ and every element of $B$ is in $A$

Which is symbolically equal to 

$$
A = B \iff A \subseteq B \text{ and } B \subseteq A
$$

Here is an example to prove that that one set is equal to another :

## Example

Let $A = \{m \in \mathbb{Z} \mid m = 2a \text{ for some integer } a\}$ and $B = \{n \in \mathbb{Z} \mid n = 2b - 2 \text{ for some integer } b\}$. Prove that $A = B$.

Since $A = B \iff A \subseteq B \text{ and } B \subseteq A$, both subset relations must be proved.

**Part 1 — Proof that $A \subseteq B$:**

Suppose $x$ is a particular but arbitrarily chosen element of $A$. By definition of $A$, there is an integer, say $a$, such that $x = 2a$.

Let $b = a + 1$.

Then $b$ is an integer because it is a sum of integers.

Also $2b - 2 = 2(a + 1) - 2 = 2a + 2 - 2 = 2a = x$.

Thus, by definition of $B$, $x$ is an element of $B$. $\blacksquare$

**Part 2 — Proof that $B \subseteq A$:**

Suppose $x$ is a particular but arbitrarily chosen element of $B$. By definition of $B$, there is an integer, say $b$, such that $x = 2b - 2$.

Let $a = b - 1$.

Then $a$ is an integer because it is a difference of integers.

Also $2a = 2(b - 1) = 2b - 2 = x$.

Thus, by definition of $A$, $x$ is an element of $A$. $\blacksquare$

Since $A \subseteq B$ and $B \subseteq A$, we conclude $A = B$.
