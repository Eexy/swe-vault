A **Boolean algebra** is a [[set]] $B$ together with two operations denoted $+$ and $\cdot$ such that for all $a$ and $b$ in $B$ both $a+b$ and $a \cdot b$ are in $B$ and the following axioms are assumed to hold

1. **Commutative Laws** : For all $a$ and $b$ in $B$ :
$$
a + b = b+a
$$
$$
a \cdot b = b \cdot a
$$
2. **Associative Laws** : For all $a$, $b$ and $c$ in $B$
$$
(a+b)+c = a+(b+c)
$$

$$
(a \cdot b) \cdot c = a \cdot (b \cdot c)
$$
3. **Distributive Laws** : For all $a$, $b$  and $c$ in $B$
$$
a + (b \cdot c) = (a+b) \cdot (a+c)
$$
$$
a \cdot (b+c) = (a \cdot b) + (a \cdot c)
$$
4. **Identity Laws**: There exist distinct elements ) and ! in $B$ such that for each $a$ in $B$
$$
a + 0 = a
$$
$$
a \cdot 1 = a
$$
5. **Complement Laws** : For each $a$ in $B$, there exists an element in $B$, denoted $\overline{a}$ and called the **complement** or **negation** of $a$ such that
$$
a + \overline{a} = 1
$$
$$
a \cdot \overline{a} = 0
$$

## Properties of a Boolean algebra

Let $B$ be any Boolean algebra

1. **Uniqueness of the Complement Laws** : For all $a$ and $x$ in $B$, if $a+x=1$ and $a \cdot x = 0$ then $x = \overline{a}$
2. **Uniqueness of 0 and 1**: If there exists $x$ in $B$ such that $a + x = a$ for every $a$ in $B$ then $x = 0$ and if there exists $y$ in $B$ such that $a \cdot y = a$ for every $a$ in $B$ then $y = 1$
3. **Double complement Law** : For every $a \in B$ $\overline{(\overline{a})} = a$
4. **Idempotent Laws** : For every $a$ in $B$
$$
a+a = a
$$
$$
a \cdot a = a
$$
5. **Universal Bound Laws** — For every $a \in B$, 
6. $$a + 1 = 1$$ $$a \cdot 0 = 0$$ 6. **De Morgan's Laws** — For all $a$ and $b \in B$, 
$$\overline{a + b} = \bar{a} \cdot \bar{b}$$ $$\overline{a \cdot b} = \bar{a} + \bar{b}$$ 7. **Absorption Laws** — For all $a$ and $b \in B$ 
$$(a + b) \cdot a = a$$ $$(a \cdot b) + a = a$$ 8. **Complements of 0 and 1**: 
$$\bar{0} = 1$$ $$\bar{1} = 0$$