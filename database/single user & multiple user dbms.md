---
id: single user & multiple user dbms
aliases: []
tags: []
---
# Single user and multi user dbms

## Single user dbms

 A [[DBMS]] is said to be **single user** if only one user can be connected at a
time.

## Multi user dbms

A [[DBMS]] is said to be **multi user** if multiple user can be connectedd at a
time

In multi user dbms we need to handle [[transaction]] in a controlled manner or
else we could have multiple problems

### The lost update problem

This problem occurs when two transactions that access the same database items
have their operations interleaved in a way that makes the value of some database
items incorrect

**example** : If we have two transaction $T1$ and $T2$ that access a database
for flight reservation. If T1 remove 5 seat available and T2 add 4 seat available and at
the start we have 80 seat availables. Because those 2 transactions happens at
the same time we could have T2 that overwrite T1 so in the database we would
have 84 seats available when in reality we only have 79

### The dirty read problem

This problem occurs when one transaction updates a database and then the
transaction fails for some reason. If another transaction read the database
before the first one rollback then the second transaction would have read
invalid data

### The unrepeatable read problem

This problem occurs when one transaction must readds the same item twice and
then another transaction update it between the first and second read

### The inccorect summary problem

This problem occurs when one transaction is calculating an aggregate summary
function on a number of items while other transactions are updating the same
items. In this case that means that the transaction that is doing the operation
may calculate some values before they are updated and some values after they
have been updated which result in an invalid result
