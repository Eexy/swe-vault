---
id: attribut
aliases: []
tags: []
---
# Attribut

An **attribut** is a property of an [[entity]]. Each attribut has a value

## Composite and atomic attribut

A composite attribut is an attribut that can be divided into smaller subpart

**exemple** : an address attribut can be divided like thath :

- street's name
- street's number
- zip code
- city

An **atomic attribut** is an attribut that can't be divided

**exemple** : We can't divide a name

## Single-valued and multivalued attribut

A **single valued attribut** is an attribut that can only contains one value

**exemple** : an `age` attribut can only contains one numer

A **multivalued attribut** is an attribut that can contains multiple value at
the same time

**exemple** : An attribut `color` on a car entity can contains multiple values
for each color the cas has

## Stored and derived attribut

A **stored attribut** is a attribut that is save into the db

A **derived attribut** is an attribut that can be derived from another one

**exemple**: We can derived an `age` attribut fron a `birthdate` attribut so
that we only store the last one

## NULL values

A **nullable attribut** is an attribut that can have the `NULL` value
