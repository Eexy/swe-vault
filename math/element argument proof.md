---
id: element argument proof
aliases: []
tags: []
---
# Element argument proof

The *element argument proof* is the basic method of [[proof]] to prove that one
[[set]] is a [[subset]] of another

It follow these step

Let sets $X$ and $Y$ be given. To prove that $X \subseteq Y$

1. *suppose* that $x$ is a particular but arbitrarily chosen element of $X$
2. *show* that $x$ is  an element of $Y$

## Example

Let $A = \{x \in \mathbb{Z} \mid x = 6r + 12 \text{ for some integer } r\}$ and $B = \{x \in \mathbb{Z} \mid x = 3s \text{ for some integer } s\}$. Prove that $A \subseteq B$.

**Proof Outline:**
- *Starting Point:* Suppose $x$ is a particular but arbitrarily chosen element of $A$.
- *To Show:* $x$ is an element of $B$.

**Proof:**

Suppose $x$ is a particular but arbitrarily chosen element of $A$.

By definition of $A$, there is an integer, say $r$, such that $x = 6r + 12$.

Let $s = 2r + 4$.

Then $s$ is an integer because products and sums of integers are integers, and so $3s \in B$ by definition of $B$.

Also $3s = 3(2r + 4) = 6r + 12 = x$.

Thus, by definition of $B$, $x$ is an element of $B$. $\blacksquare$

**Note:** $B \not\subseteq A$. To disprove $B \subseteq A$, we need an element of $B$ that is not in $A$ — i.e., an integer of the form $3 \cdot (\text{some integer})$ that cannot be written as $6 \cdot (\text{some integer}) + 12$. Take $x = 3$: then $x \in B$ since $3 = 3 \cdot 1$, but $x \notin A$ because there is no integer $r$ such that $3 = 6r + 12$:

$$6r + 12 = 3 \implies 2r + 4 = 1 \implies 2r = -3 \implies r = -3/2$$

But $-3/2$ is not an integer. Thus $3 \in B$ whereas $3 \notin A$, so $B \not\subseteq A$.
