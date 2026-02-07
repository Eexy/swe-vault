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

## Clustering indexes
