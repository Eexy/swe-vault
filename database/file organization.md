---
id: file organization
aliases: []
tags: []
---

# File organization

A **file organization** specify how in a [[file & records#File|file]]
[[file & records#Record|record]] are organized

We disting two types of file of organization

## Heap file

An **heap file** is the most basic file organization where record are stored in a random
order across the different [[page]] of the file. Most of the time in a heap file
record are stored in the order they were inserting

Because the records are inserting at the end of the file it's very efficient to
insert new data but because of this searching a record involve a linear search
so it can become very slow

## Ordered file

An **ordered file** is a file organization where records are ordered based on
the value of one of their fields. This fields is called the **ordering field**.

When the field is a **key field** which is a field which have a unique value for
each record then it's called a **ordering key**

In contrary to an heap file searching a record is very efficient but inserting /
deleting one is slower because the record must remain physically order

**example** Let say I have a file that store records of persons where the
ordering field is the `age`

| Id  | Name | Age |
| --- | ---- | --- |
| 1   | Alex | 1   |
| 2   | Axel | 3   |

If I want to insert a new person with `age = 2` I first have to move the second
record and insert a new one in between

To find a record in an ordered file we can use a [[binary search]]

## Clustered file

A **cluster file** is also an ordered file where records are ordered based on a
non key field

The field use is called the **clustering field**

## Hash file

An **hash file** is a file organization where records are ordered based on an hash.

This organization provides very fast access to records under certain search
conditions. It's important that the condition must be an equality condition on a
single field

To create and hash file we apply an **hash function** $h$ on a record field that
we call the **hash field**. If the field is also the record key we call it the
**hash key**
