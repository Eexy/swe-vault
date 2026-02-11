---
id: multi level indexes
aliases: []
tags: []
---
# Multi level indexes

A **multi level index** is an index build on top of a 
[[single level ordered indexes]]

In a single level ordered index we find the index entry we are interested in by
applying a [[binary search]] to find the value and then accesing the [[page]]
where the data is. So to find the right index entry we need approximately 
$log_2(b_i)$ operations to traverse the index / the pages of our index where $b_i$ is the number of 
$page$ or entries in our index

The idea behind a multi level index is to reducte the part of the index that we
continue to search by $bfr_i$ (we can call it the **blocking factor**) which means that we will slice 
our single index file in subpart/slice and each entry of our multi level index will point 
to one of the subpart so when we have found the right slice in our single level index we 
then search for the correct entry and the go to the right data page

The value $bfr_i$ is called the **fan out** (We abbreviate it **fo**). This fan
out will divide our single index file in $n$ slices so searching a multi level
index cost approximately :

$$
log_fo(b_i) + 1
$$

Where we have $fo = n$ and we add 1 to accounts for the final page access

**important**: This approach is only faster if the fo is superior to 2 else we
get back to the same number of operations that with a single level index

This give us the following schema :

![[database/multilevel_index.png]]

A multi level index is an ordered file with **distinct** value for each index
entry. In a multilevel index the first index is called the **first level** then the
index we create on it is called the **second level**

The second level will use a 
[[single level ordered indexes#primary-indexes|primary index]]. Because it's a
primary index we use **block anchor** so that the second level has one entry for
each **page** of the first level

The blocking factor is calculate with following formula

$$
fo = bfr_i = \lfloor(P / E)\rfloor
$$

Where $P$ is the [[page]] size in bytes and $E$ is the size in bytes of a single
index entry

Furthemore the number of entries in our second level is calculated like that :

$$
\lceil(r_1/fo)\rceil
$$

where $r_1$ is the number of entries in the first level


One advantage of the multi level index approach is that we can keep creating new
level. For example we could create a third level to index our second etc...

**important**: We required a second level only if the first level occupies more than
one page same thing with the second level. We required a third level only if the
second level occupies more than one page..
