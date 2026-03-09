---
id: dbms journal
aliases: []
tags: []
---
# DBMS journal

To be able to recover from failures that affect [[transaction]] the
[[DBMS]] keep track of all transaction operations that affect the values of
[[database]] items a well as other transaction information the may be needed to
permit recovery from failures in a log file. This log file is also named the
**DBMS journal**

This file is a sequential, append-only file that is kept on disk. It should be
save to restored the database in the case of a catastrophic failure

## Log records

Each entry of the log file is called  **log records**

Here is all the type of entries and the corresponding action 

- `[start_transaction, T]` : Indicates that transaction $T$ has started
- `[write_item, T, X, old_value, new_value]` : Indicates that transaction T has
  changed the value of database item $X$ from old value to new value
- `[read_item, T, X]` : Indicates that transaction $T$ has read the vlaue of
datbase item $X$
- `[commit, T]` : Indicates that transaction $T$ has completed successfully and
  affirms that its effect can be committed to the [[database]]
- `[abort, T]` : Indicates that transaction $T$ has been aborted
