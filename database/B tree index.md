---
id: B tree index
aliases: []
tags: []
---
# B tree index

A **B-tree index** is a kind of [[multi level indexes]] that uses a [[B+ tree]] 
to organize records by a **search key** (a column or set of columns chosen at 
creation time).

- **Internal nodes** store keys for navigation only
- **Leaf nodes** store the search key + a pointer to the actual row (or the 
  row itself in a clustered index)
- Leaf nodes are **linked**, enabling efficient range queries

The index keeps data sorted by the search key, allowing O(log n) lookups 
instead of full table scans.
