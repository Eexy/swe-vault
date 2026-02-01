---
id: normal form
aliases: []
tags: []
---
# Normal form

A **normal form** caracterize the fact that a [[relation]] meets certains
constraints

There is multi level of normal form :
- [[#1NF : First normal form]]
- [[#2NF : Second normal form]]
- [[#3NF : Third normal form]]
- [[#BCNF : Boyce-Codd normal form]]

The main goal with implementing normal form is to reduce the risk of
[[anomaly|anomalies]] and to avoid data redundancy

## 1NF : First normal form

The first normal form **1NF** allow only
[[attribute#composite-and-atomic-attribute|atomic attribute]]

**example** : let's say we have an ORDERS relation



|IdOrder|Client|Products|
|---|---|---|
|1|Dupont|Livre, Stylo, Cahier|
|2|Martin|Classeur, Crayon|


We saw that the `Products` column contains multiple values for each row


Which create two problems :
1. It's hard to find a product
2. Adding/removing a product is hard

We can fix both those probleme by only using atomic values for the `Products`
column


|IdOrder|Client|Produit|
|---|---|---|
|1|Dupont|Livre|
|1|Dupont|Stylo|
|1|Dupont|Cahier|
|2|Martin|Classeur|
|2|Martin|Crayon|


By doing that if we want to add a new product to a command we simply add a tuple


## 2NF : Second normal form

The second normal form **2NF** is based on the concept of 
[[functional dependencies#full-fonctional-dependency|full fonctional dependency]] which means
that every **[[relation#prime-attribute|non prime attribute]]**  must be determined by the primary key

**example** : If we take our `ORDERS` relations and that we want to add the
price for each product we could add a price `Price` column


| IdOrder | Client | Product  | Price | Date |
| ---------- | ------ | -------- | ----------- | ------------ |
| 1          | Dupont | Livre    | 25€         | 10/01/2023   |
| 1          | Dupont | Stylo    | 3€          | 10/01/2023   |
| 2          | Martin | Classeur | 7€          | 15/01/2023   |


To dertemine the price we could say that our primary key is composed of the
`IdOrder` and `Product` attribute but with that their is a problem.

The price only depend of the product so if each time their is a new
[[relation#tuple|tuple]] in our relation we would have to save the price again.
We have created a redundancy

To fix this problem we can remove the `Price` column from our relation and only
keep our `IdOrder` as our key

By doing thath we now create a new relation `Products` with the product's name
as key and we get

`ORDERS`

| IdOrder | Product  |
| ---------- | -------- |
| 1          | Livre    |
| 1          | Stylo    |
| 2          | Classeur |


`PRODUCTS`

| Products | Price |
|---------|-------------|
| Livre | 25€ |
| Stylo | 3€ |
| Classeur | 7€ |


Now we don't have to save the price each time and when the price evolve all
orders are updated

## 3NF : Third normal form

The third normal form **3NF** is based on 
[[functional dependencies#transitive-functional-dependency|transitive dependency]]. A relation 
is **3NF** if there is no transitive dependency which means that all non
[[relation#prime-attribute|non prime attribute]] must be determined directly from
the primary key

**example**: Let's say we have a relation `EMPLOYEE`


| IdEmployee | Name | Department | DepartmentManager |
|-----------|-----|-------------|------------------------|
| 1 | Dubois | Informatique | Moreau |
| 2 | Leroy | Marketing | Petit |
| 3 | Thomas | Informatique | Moreau |

In this relation with the employee'id we can determine the his department but we
also see that with the department we can determine the manager

The probleme with that is that if we have multiple employees working in the same
department we create a redundancy on the department manager but also that if we
need to update a manager we need to do it for all the tuples or else we could
create an [[anomaly]]

To fix that we create a new relation `DEPARTMENT`


| Department | manager |
|-------------|------------------------|
| Informatique | Moreau |
| Marketing | Petit |


We update our `EMPLOYEE` relation


| IdEmployee | Name | Department |
|-----------|-----|-------------|
| 1 | Dubois | Informatique |
| 2 | Leroy | Marketing |
| 3 | Thomas | Informatique |


Now when we need to update one of our manager we only do it once

## BCNF : Boyce-Codd normal form

The **Boyce-Codd normal form** is based on the third-normal form. It is a
strictier version of it

To have a relation that respect the BCNF that means that for any functional
dependency $X \rightarrow Y$ then $X$ must be a [[key#candidate-key|candidate key]]

**example**: Let say we have a relation `TEACH` that store each student with
their course and the teacher



| Student | Course | Teacher |
|-----------|-----|-------------|
| Cindy | Math | Pythagore |
| Matheo | Math | Pythagore |
| Melanie | Marketing | Jobs  |


We can see that we have three functional dependency
1. {StudentId, Course} determine Teacher
2. {teacher} determine course
3. {Student, Teacher} determine course

The problem is that `Teacher` is not a key so if we delete `Melanie` we lose the
information that Jobs teach `Marketing`

To remedy that we need to decouple this relation like that

`Teacher`


|  Course | Teacher  |
|-----|-------------|
| Math | Pythagore |
| Math | Pythagore |
| Marketing | Jobs  |


`Teach`


| Student | Teacher |
|-----------|-----|
| Cindy |   Pythagore |
| Matheo |   Pythagore |
| Melanie |  Jobs  |



