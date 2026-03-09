---
id: ACID
aliases: []
tags: []
---
# ACID

**ACID** is an acronym for **atomicity**, **consistency preservation**,
**isolation** and **durability**

## Atomicity

A [[transaction]]is an atomic unit of processing. It should either be performed in
its entirety or not performed at all

## Consistency preservation

A [[transaction]] should be consistency preserving meaning thaat if it
completely executed from beginnning to end without interference for other
transactions it should take the [[database]] from one consistent state to anoter

## Isolation

A [[transaction]] should appear as though it is being executed in isolation from
other transaction even though mnany transactions are executing concurrently.
This means that the execution of a transaction should not be interfered with by
any other transactino

## Durability

The changes applied to the database by a commmited [[transaction]] must persit
in the database. These changes must not be lost because of any failure
