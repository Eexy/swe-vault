---
id: absolute value and triangle inequality
aliases: []
tags: []
---
# Absolute value and triagnle inequality

## Absolute value

For any real number $x$, the **absolute value of x** denoted $|x|$, is defined
as follows

$$
|x| = \begin{cases} x & \text{if } x \geq 0 \\ -x & \text{if } x < 0 \end{cases}
$$

**examples** : $|5| = 5$, $|-3| = -(-3) = 3$, $|0| = 0$

## Triangle inequality

The **triangle inequality** says that the absolute value of the sum of two
numbers is less than or equal to the sum of their absolute values

For all real numbers $x$ and $y$, $|x + y| \leq |x| + |y|$

**example** : $|3 + (-7)| = |-4| = 4 \leq |3| + |-7| = 3 + 7 = 10$

**Proof.** Suppose $x$ and $y$ are any real numbers.

**Case 1 ($x + y \geq 0$):** In this case $|x + y| = x + y$, and so by
[[#lemma-454|Lemma 4.5.4]], $x \leq |x|$ and $y \leq |y|$. Hence

$$
|x + y| = x + y \leq |x| + |y|
$$

**Case 2 ($x + y < 0$):** In this case $|x + y| = -(x + y) = (-x) + (-y)$,
and so by Lemmas 4.5.4 and 4.5.5,

$$
-x \leq |-x| = |x| \quad \text{and} \quad -y \leq |-y| = |y|
$$

It follows that

$$
|x + y| = (-x) + (-y) \leq |x| + |y|
$$

Hence in both cases $|x + y| \leq |x| + |y|$. $\blacksquare$

### Lemma 4.5.4

For every real number $r$, $-|r| \leq r \leq |r|$

**example** : Let $r = -3$. Then $|r| = 3$, so $-3 \leq -3 \leq 3$ 

**Proof.** Suppose $r$ is any real number. We divide into cases according to
whether $r = 0$, $r > 0$, or $r < 0$.

**Case 1 ($r = 0$):** By definition of absolute value, $|r| = r = 0$. Since
$0 = -0$, we have $-|r| = 0 = r = |r|$, and so it is true that

$$
-|r| \leq r \leq |r|
$$

**Case 2 ($r > 0$):** By definition of absolute value, $|r| = r$. Also, since
$r$ is positive and $-|r|$ is negative, $-|r| < r$. Thus it is true that

$$
-|r| \leq r \leq |r|
$$

**Case 3 ($r < 0$):** By definition of absolute value, $|r| = -r$. Multiplying
both sides by $-1$ gives $-|r| = r$. Also, since $r$ is negative and $|r|$ is
positive, $r < |r|$. Thus it is also true in this case that

$$
-|r| \leq r \leq |r|
$$

Hence, in every case, $-|r| \leq r \leq |r|$. $\blacksquare$

### Lemma 4.5.5

For every real number $r$, $|-r| = |r|$

**example** : $|-(-4)| = |4| = 4$ and $|-4| = 4$, so $|-(-4)| = |-4|$ 

**Proof.** Suppose $r$ is any real number. If $r > 0$ then $-r < 0$, and if
$r < 0$ then $-r > 0$. Thus

$$
|-r| = \begin{cases} -r & \text{if } -r > 0 \\ 0 & \text{if } -r = 0 \\ -(-r) & \text{if } -r < 0 \end{cases}
\quad \text{by definition of absolute value}
$$

$$
= \begin{cases} -r & \text{if } -r > 0 \\ 0 & \text{if } r = 0 \\ r & \text{if } -r < 0 \end{cases}
\quad \text{since } -(-r) = r \text{, and when } -r = 0 \text{ then } r = 0
$$

$$
= \begin{cases} -r & \text{if } r < 0 \\ 0 & \text{if } r = 0 \\ r & \text{if } r > 0 \end{cases}
\quad \text{since when } -r > 0 \text{ then } r < 0 \text{, and when } -r < 0 \text{ then } r > 0
$$

$$
= \begin{cases} r & \text{if } r \geq 0 \\ -r & \text{if } r < 0 \end{cases}
\quad \text{by reformatting the previous result}
$$

$$
= |r| \quad \text{by definition of absolute value} \quad \blacksquare
$$

