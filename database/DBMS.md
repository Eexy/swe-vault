---
id: DBMS
aliases: []
tags: []
---

# DBMS

A **DBMS** (Database management system) is a computerized system that enables
users to create and maintain a [[database]]. It facilitates the process of
**defining**, **constructing**, **manipulating** and **sharing** databases among various users
and application

## Defining a database

Defining a database involves specifying the data types, structures and
constraints of the data to be stored 

## Constructing

Constructing a database is the process of stroing the data on some storage
medium that is controlled by the DBMS

## Manipulating

Manipulating a database includes functions such as querying the database to
retrieve specific data, updating the database to reflect changes in the
miniworld...

## Sharing

Sharing a database allows multiple users and programs to access the database
simultaneously

## Advantages of using a DBMS

Using a DBMS offers multiple advantages

### Controlling redundancy

The use of DBMS allows us to reduce redundancy of data

### Restricting unauthorized access

A DBMS allows us to restrict some informations to specific users via a its
security and authorization subsystem

### Providing backup an recovery

DBSM provides falities for recovering from hardware of software failures. The
backup and recovery subsystem is responsible for recovery

### Providing stroage structures and seaarch techniques for efficient query processing

DBMS must provide capabilities for efficiently executing queries and updates.
Because the database is typically stored on disk the DBMS must provide
specialized data structures and search techniques to speed up disk search for
the desired record like the use of [[index]]

The query processing and optimization module of the DBMS is responsible for
choosing and efficient [[query plan]] for each query based on the existing
storage structures

### Representing complex relationships among data

A DBMS allow the users to have the capability to represent a variety of complex
relationships among the data, to define new relationships and to retrieve and
update related data easily and efficiently
