---
id: query plan
aliases: []
tags: []
---
# Query plan

A **query plan** is a roadmap the [[DBMS]] creates to execute a [[SQL]] query
efficiently. The query plan explains all the operations the dbms do

## Purpose of using a query plan

Reading the query plan has 3 purposes

1. Efficiency : The plan ensures that the database engine uses the most
   efficient path to execute a query. 
2. Transparency : By studying the plan, developers gain insights into how the
   [[DBMS]] works
3. Optimization : It highlights potential bottlenecks such as unnecessary index
   usage or costly operations like full table scans

## Type of query plan

### Estimated execution plan

The **estimated execution plan** previews how the [[DBMS]] intends to execute a
query. It is generated before the query is run using information about the
[[database]]

It is ideal for anlyzing the potential impact of a query especially when working
with large dataset where executing the query could be time-consuming or
disruptive

### Execution plan

The **execution plan** is generated after the query has been executed. It
includes real runtime statistics making an useful tool for diagnosing
performance issue

## Key elements

A query plan is composed of multiples elements that impact the performance of
the query

### Operators

Operators represent action like scanning tables, filtering rows or performing
joins. These tasks dictage how data is fetched and processed

### Execution order

The execution order determines the logical sequence in which the [[DBMS]]
processes the query. Unlike the [[SQL]] syntax the engine typically begins with
retrieving data, proceeds to filters, join aand aggregations before delivering
the final result. Optimizing this order such as applying filters earlier can
reduce the workload on subsequent operations

### Cost metrics

Cost metrics are essential indicators of the resources needed for each operation
in the pan. These metrics include CPU and I/O costs and help identify the most
resource intensive steps. For example a high I/O cost may signal that a large
amount of data is being read from disk which could be addressed by better
indexing or query restructuring

### Index usage

Index usage is critical to optimizing query performance. Efficient use of
indexes like index seeks or covering indexes can significanlty speed up data
retrieval and reduce the reliance on full table scans. Poor index usage often
manifests as bottlenecks in execution plans making it as key area for
optimization

### Cardinaly and row estimates

Cardinality and row estimates indicate the predicted number of rows processed at
each query stage. These estimates guide the [[DBMS]] in selecting the most
efficient execution strategy. However inacuuracies in these predictions are due
to outdated statistics or complex query structures. This can lead to inefficent
operations such as unnecessary joins or excessive memory usage

## Common pitfalls in query execution plans

Here is the list of common behaviour that can create ineffiencies and impact
performance

### Full table scan

A full table scan occurs when the [[DBMS]] reads all rows in a table to satisfy
a query. While sometimes unavoidable, it's often a sign of missing or improperly
used indexes

**solution** : Create indexes on frequently filtered or joined columns to avoid
unnecessary full table scans

### Overuse of nested loops

Nested loops are a join strategy where the databse iterates through each row of
one table to find matching rows in another. While efficient for small datasets
the loops can become a bottleneck with larger tables

**solution** : Optimize joins with indexes or switch to hash or merge join for
larger dataset

### Missing or outdated statistics

Query optimization heavily relies on accurate statistics about table data
distribution. Missing or outdated statistics can lead to inefficient execution
plan

**solution** : Update regularly statistics to ensure the [[DBMS]] has accurate
information

### Expensive sort and aggregation operations

Sorts and aggregations can consume significant resources especially on large
datasets

**solution** : Use indexes that match the query's sorting or grouping criteria
to minimize resource usage

### Overlooking query execution order

The logical order of operations in a query can sometimes lead to inefficiencies
such s filtering data late in the execution process

**solution** : Rewrite queries to apply filters earlier in the execution process

## Generate and read execution plan in postgres

Ressource : [https://www.postgresql.org/docs/9.5/using-explain.html](postgres plan)

### Generate plan

#### Generate execution plan

To generate an execution plan in postgres we have to add the statement 
`EXPLAIN ANALYZE` before our query. Doing that postgres will execute the query
and generate the execution plan

#### Generate estimated plan

To generate the estimated execution plan we have to add the statem `EXPLAIN`
before our query. In this case postgres estimate what it will do when executing
the query but will not really executing it

### Read plan

When creating a plan postgres will create a node of all the operations

```txt
Sort  (cost=717.34..717.59 rows=101 width=488) (actual time=7.761..7.774 rows=100 loops=1)
   Sort Key: t1.fivethous
   Sort Method: quicksort  Memory: 77kB
   ->  Hash Join  (cost=230.47..713.98 rows=101 width=488) (actual time=0.711..7.427 rows=100 loops=1)
         Hash Cond: (t2.unique2 = t1.unique2)
         ->  Seq Scan on tenk2 t2  (cost=0.00..445.00 rows=10000 width=244) (actual time=0.007..2.583 rows=10000 loops=1)
         ->  Hash  (cost=229.20..229.20 rows=101 width=244) (actual time=0.659..0.659 rows=100 loops=1)
               Buckets: 1024  Batches: 1  Memory Usage: 28kB
               ->  Bitmap Heap Scan on tenk1 t1  (cost=5.07..229.20 rows=101 width=244) (actual time=0.080..0.526 rows=100 loops=1)
                     Recheck Cond: (unique1 < 100)
                     ->  Bitmap Index Scan on tenk1_unique1  (cost=0.00..5.04 rows=101 width=0) (actual time=0.049..0.049 rows=100 loops=1)
                           Index Cond: (unique1 < 100)
 Planning time: 0.194 ms
 Execution time: 8.008 ms
```

This plan must be read from bottom to top where at the bottom we have the first
operation

On each operation we can see we have multiple information. First we have the
difference between **actual** and **cost**. Actual represent what really happened
and cost is an estimated guess

- `time` : represent the time it took. If this operations is repeated multiple
  times then it's correspond to the average of all the iterations multiply by
the loop counter
- `rows` : number of rows returned
- `loop` : indicate if this operations has been executed multiple time
- `witdh` : is the estimated size in bytes of the returned rows. In this case we
  have 0 because we don't retrieve any rows
