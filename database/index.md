---
id: index
aliases: []
tags: []
---

# Index

An **index** is an auxiliary **access structure** to speed up quierying
[[file & records#Record|records]] based on a certains condition.

The index structures are additional files on disk that provide a secondary access path which
provide alternative ways to access the records without affecting the physical
placement of records

They are built based on the **indexing fields**. One of the advantage to use an
index is that we can create one based on multiple field

## Indexing field

An **indexing field** is a [[file & records#Record|record]] field use to
construct an index. Any field can be used
