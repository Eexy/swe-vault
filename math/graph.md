---
id: graph
aliases: []
tags: []
---
# Graph

A **graph** $G$ consists of two finite [[set|sets]] : **vertices** and **edge**

![[math/graph/graph.png]]

## Vertice

The set of vertices in a graph is a nonempty set denoted $V(G)$

### Adjacent vertice

Two vertices are called **adjacent** if they are connected by an **[[#Edge|edge]]*

An vertice is said to be **adjacent to itself** if its part of a loop

### Isolated vertice

A vertice is called **isolated** if they are no edge associated to it

### Degree

The **degree** of a vertice $v$ in a graph $G$ denoted $deg(v)$ equals the
numbers of [[#Edge|edge]] thare are incident on $v$. If there is a [[#Loop|loop]] then the edge is
counted twice

## Edge

The set of edge in a graph is denoted $E(G)$. An edge is associated with a set
consisting of either one or two vertices that we call its **endpoint** 

An edge is said to be **incident on** each of its endpoint

### Loop

A **loop** is an edge that only have one endpoint

### Parallel edges

Two or more distinct edges are called **parallel** if they share the same set of
endpoints

### Adjacent

Two edges are said to be **adjacent** if they are incident on the same endpoint
