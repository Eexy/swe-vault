
# Relation induced by a partition

Given a [[partition]] of a [[set]] $A$, the **[[math/relation|relation]] induced by the partition**, $R$, is defined on $A$ as follows :

For every $x,y \in A$

$$
xRy \leftrightarrow \text{there is a subset } A_i \text{ of the partition such that both } x \text{ and } y \text{ are in } A_i
$$

Example :

Let $A = \{0,1,2,3,4\}$ and consider the following partition of $A$ :

$$
\{0,3,4\}, \{1\}, \{2\}
$$
We need to find $R$ the relation induced by this partition

Since $\{0,3,4\}$ is a subset of the partition we have 

$$
0R3, 3R0, 0R4, 4R0, 4R3, 0R0, 3R3 \text{ and } 4R4
$$
Since $\{1\}$ is a subset of the partition

$$
1R1
$$

And since $\{2\}$ is a subset of the partition

$$
2R2
$$
Hence we have

$$
R = \{(0,0),(0,3),(0,4),(1,1),(2,2),(3,0),(3,3),(3,4),(4,0),(4,3),(4,4)\}
$$

The fact is that a relation induced by a partition of a set satisfies all three properties : [[math/relation#Reflexivity, Symmetry and transitivity|reflexivity, symmetry and transitivity]]

