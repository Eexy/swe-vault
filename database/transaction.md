---
id: transaction
aliases: []
tags: []
---
# Transaction

A **transaction** is a logical unit of work composed of one or multiple
operations that must be completed entirely to ensure correctness. 
If there is an error all the operations of the transaction are cancelled

We commonly defined the start and the end of a transaction in [[SQL]] with

```sql
BEGIN TRANSACTION;

END TRANSACTIONS;
```

Between those two statements we put all the operations we need to effectuate

## Read only / read write transaction

We say a transaction is **read only** when all the operations in the transaction
only read from the [[database]]. If we write (insert/update) we say the
transaction is a **read-write transaction**

## Transaction State

He is the state that follow a transaction

![[database/transaction_state.png]]

- `BEGIN_TRANSACTION`: Marks the beginning of the transaction execution
- `READ` or `WRITE`: specify read or write operations on the database items that
  are executed as part of a transaction
- `END_TRANSACTION`: Marks the en of the transaction execution. However it may
be necessary to check whether the changes introduce by the transaction can be
permanently applied or if we need to abort
- `COMMIT` or `COMMIT_TRANSACTION`: : Signals a successful end of the
transaction so that any changes can be safely **committed** and will not be
undone
- `ROLLBACK` or `ABORT` : Signals that the transaction has failed so we need to
  undone all changes made

## SQL

In SQL the definition of a transaction is the same as defined above. The
particularity is that a single statement is always considered
[[ACID#atomicity|atomic]] meaning that if it's fail it's canceled meaning that a
transaction is created implicitly without specifying

However if we need to do multiple operations we need to specify a transaction
with the keywords `BEGIN TRANSACTION` and `END TRANSACTION`.

We can specified the type of transaction with the keyword `READ ONLY` or 
`READ WRITE`. By default a transaction is `READ WRITE`
