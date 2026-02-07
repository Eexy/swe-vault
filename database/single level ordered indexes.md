---
id: single level ordered indexes
aliases: []
tags: []
---

# Single level ordered indexes

A **single level ordered index** is an index based on the same ideas as indexes
in a textbook. An index in a text book lists important terms at the end of
the book in alphabetical order with their page number. With the index we can
search for a certain term to find the a list of addresses (page) where the word
is then go to it and search the page

For a file with a given record structure consisting of several fields
([[attribute]]) an index is usually defined on a single field which is the
[[index#index#indexing-field|indexing field]]. The index will stores each value
of the index field along with a list of pointer to all pages that contain
records with that field value

The values in the index are ordered so that we can do a binary search on it and
rapidly identify where the value are

## Primary indexes

A **primary index** is an [[file organization#ordered-file|ordered file]] whose records are of fixed length with
two fields. It acts like an access structure to efficiently search for and
access [[file & records#record|records]] 

A primary index is only specified on an ordered file

The first field is of the same data type as the ordering key field on the data
file called the **primary key** and the second field is a point to a [[page]]. 

There is one **index entry** in the index file for each [[page]] in the data
file

Each index entry has the value of the primary key field for the first record in
a [[page]] and a pointer to that [[page]]

We write an index entry like that

- $<K(i), P(i)>$
- $<K(i), X>$

It correspond to that

- $X$ may be the physical address of a [[page]] in the file as in the case of
$P(I)$
- $X$ may bbe the record address made up of a [[page]] address and a 
[[file & records#record|record id]] 
- $X$ may be the logical address of the block or the record wihtin the file and
  is a relative number that would be mapped to a physical address

**example**: Example of a primary index

![[database/primary_index.png]]

In this example we use the $Name$ as the primary key assuming that each value of
$Name$ is unique and the value is the address of the [[page]]

The total number of entris in the index is the same as the number of [[page]] in
the ordered data file.

The first record in each block of data file is called the **anchor record** or
the **block anchor**

A major problem with a primary index is that insertion an deletion of records is
not efficient because we first have to update the ordered data file and then we
have to do the same step for the index

## Clustering indexes

A **clustering index** is an index that it use for 
[[file organization#clustered-file|clustered file]].

A clustring index is also an ordered file with two fields :
- The first field is of the same type as the clustring field of the data file
- The second fild is a [[page]] pointer

There is one entry in the index for each **distinct value** of the clustering
field and it contains the value and a pointer to the fist page in the data file
that has a record with that value for its clustering field

![[database/clustering_index.png]]

## Secondary indexes

A **secondary index** provides a secondary ways to access a data file for which
some [[#Primary indexes|primary index]] already exist. The data file records could be 
ordered, unordered or hashed

A secondary index could be created on a fild that is a candidate key and has a
unique value for each record or a nonkey field with duplicate values

The secondary index is again an ordered file with two fields. The first field is
of the same data type as some nonordering field of the data file and the second
field is either a [[page]] pointer or a [[file & records#record]] pointer

One of the advantage of a secondary index is that we can create as many as we
want on the same file. Each of those represents an additional means of accessing
the file based on some specific field

### Secondary indexes based on unique field

When we base a secondary index on a unique field we call that field a
**secondary key**

In this case there is one index entry for each record in the data file which
contains the value of the field for the record and a pointer either to the
[[page]] in which contains the record is stored or to the record itself

Because the index is based on a unique value we can use a [[binary search]] to
find the key-value pair of the index. However because the data file is not
physically ordered we cannot use block anchor.  That is why an index entry is
created for each record in the data file rathan than for each block as in the
case of a [[#Primary indexes|primary index]]

A secondary index usually needs more storage space and longer search time than
does a primary index because of its larger number of entries. However the
improvement in search time for an arbitrary record is much greater since we
would have to do a linear search on the data file if the secondary index did not
exist

![[database/secondary_index_on_unique.png]]

### Secondary indexes based on a duplicate field

When we bases our secondary index on a nonordering, non key field that means we
have different records in the data file can have the same value for the indexing
field. In this case we have several options for implementing such an index :

1. Include duplicate endex entries with the same $K(i)$ value, one for each
   record
2. Have a variable-length records for the index entries with a repeating field
   for the pointer. So we would have a list of pointer for a field
$<P(i,1),...,P(i, k)>$ in the indexing field value equals $K(i)$
3. Keep the index entries themselves at a fixed length and have a single entry
   for each index field value but to create an extra level of indirection to
handle the multi level of pointer. In this case the pointer $P(i)$ points to a
[[page]] which contains a set of records pointer and each record pointer in that
page points to ofe of the data file records with the appropriate value $K(i)$

![[database/secondary_index_non_unique.png]]

