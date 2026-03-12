---
id: directed graph
aliases: []
tags: []
---
# Directed graph

![[math/graph/directed_graph.png]]

A [[graph]] $G$ is a **directed graph** or a **digraph** if it's composed of two sets

1. $V(G)$ a nonempty set of vertices
2. $D(G)$ a set of directed edges where each is associated with an ordered pair
   of vertices

If an edge $e$ is a associated with the pair (v,w) of vertices
then $e$ is said to be the **directed edge** from $v$ to $w$

That means that in a directed graph we have to follow the path from $v$ to $w$
but we can't go back to $v$ from $w$ if there is not a directed edge with the
associated tuple $(w,v)$
