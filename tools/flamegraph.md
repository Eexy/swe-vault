---
id: flamegraph
aliases: []
tags: []
---
# Flamegraph

![[tools/flamegraph.png]]

A **flame graph** is a way to visualize CPU time spent in a function.

A **flame graph** can help us pin down where we spend too much time doing operations.

## How to read a flame graph

In a flame graph, each operation (function) is represented by a box. Each box
(function) will have a different width.

Boxes that are above each other represent functions that have been called by
the function beneath them. This represents the stack trace. Boxes that are next
to each other represent the order of execution.

For example, if we have a box $A$ and a box $B$, and box $B$ is above box $A$,
that means function $A$ called function $B$. But if box $B$ is next to box $A$,
that means the program executed $A$ first, then $B$.

In a flame graph the X-axis shows **relative duration**. A box's width indicates
the percentage of total duration spent in that function.

So the graph is not a timeline, it's a summary of what happened over the entire
recorded duration, whether it was 10 seconds or 10 milliseconds.

## How to use a flamegraph to optimize

Because each box's width represents the relative duration of the operation, we
can use the graph to search for the widest boxes to find which operations take
the most time.

Once we have found the largest operations, we can try to optimize them to reduce
their execution time.

## Example: Web server request profiling

Below is a simplified flame graph for a web server handling a single HTTP
request. Each row is a stack frame. Width is proportional to CPU time. The
bottom row is the entry point; rows above it are the functions it called.

```
|    |       executeSQL (55%)        |      | template(20%) |json(10%)|
|    |         queryDatabase (60%)          | renderResponse (30%)   |
|auth|              processRequest (90%)                              |
|                         handleRequest (100%)                        |
```

Reading the graph:

- `handleRequest` occupies the full width — it is the root caller and accounts
  for 100% of the recorded time.
- `authenticate` (auth) is narrow — it takes roughly 10% of total time.
- `processRequest` is the widest child — 90% of time is spent inside it.
- `queryDatabase` and its child `executeSQL` dominate — database I/O is the
  clear bottleneck at ~60% of total time.
- `renderResponse` splits into `templateEngine` and `serializeJSON`.

**Where to optimize**: the widest boxes at the deepest level are
`executeSQL` (~55%) and `templateEngine` (~20%). These are the highest-leverage
targets. Caching query results or adding an index would shrink `executeSQL`,
which would visibly narrow the entire `queryDatabase` and `processRequest` bars
above it.
