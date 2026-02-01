---
id: anomaly
aliases: []
tags: []
---

# Anomaly

## Insertion anomalies

Insertion anomalies occurs when we cannot insert new data without the presence
of others data 

**examples**: Here is a relation that store student course enrollments


|StudentId|CourseId|Instructor|
|---|---|---|
|1|Database|Dr.Smith|
|2|Math|Euler|


In this relation if we want to add a new course we need to have at least one
student attach to it

To fix that we need to split the relation to have a relation that store sutdent
cours enrollments and a table to store courses

## Deletion anomalies

A deletion anomaly occurs when we delete data unintentionally causes the loss of
other important data

**example**: If we take the example of the student course enrollments above when
we delete the second student for example we lose the face that there is a Math
course

## Modification anomalies

A modification anomaly occurs when the same data is stored in multiple places.
and updating it in one place doesn't automatically update it everywhere

**example**: With the student course enrollments relation if the teacher change
for math we need to change it for every row or else we will have invalid data
