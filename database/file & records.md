---
id: file & records
aliases: []
tags: []
---

# File and records

A [[DBMS]] save data in term of [[#File|file]] and
[[#Record|record]]

## Record

Data is usually stored in the form of records. Each reacord consists of a
collection of related data values or items, where each value is formed of one or
more bytes and corresponds to a particular field of the record

Usually a records describe entites and their attributes.

**example**: An EMPLOYEE record represents an employee [[entity]] and each field
value in the record specifies some attribute of that employee

A collection of field names and their corresponding data types consitutes a
**record type** or **record format**

Each record in a file has a unique identifier called a **record id** or **rid**.
This identifier is used to localte the disk address of the [[page]] containing
the record

## File

A **file** is a sequence of records. In many cases, all records in a file are of
the same record type

A file is also a collection of [[page]]

### Fixed length record

If every record in a file has exactly the same size in bytes the file is said to
be made of **fixed-length record**

### Variable length record

If there is records with different size the file is said to be made of
**variable-length record**

### Header

A **file header** or **file descriptor** contains information about a file that
is need by the system programs that access the file

The header includes informations to determine the disk addresses of the file
blocks and also the record type

## Operations

A [[DBMS]] support different kind of operations to handle file

### Open

The **open** operation prepares the file for reading or writting. It retrieve
the file header and sets the file pointer to the beginning of the file

### Reset

The **reset** operation sets the file pointer to the beginning of the file

### Find

The **find** operation searches for the first record that satisfies a search
conditions. The found record becomes the **current record**

### Read

The **read** operation copies the current record to a program variable in the
user program

### FindNext

The **find next** operation search the next record that satisfies the search
condition

### Delete

The **delete** operation deletes the current record

### Modify

The **modify** operation modifies some fields of the current records

### Insert

The **insert** operation inserts a new record in the file by location the
block where the record is to be inserted

### Close

The **close** operation close the file and can perform some cleanup operations

### FindAll

The **find all** operations searches for all the record that satisfies a search
condition

### Find n

The **find n** operations searches for all the records that satisfies a search
condition and limit the number of result to $n$

### FindOrdered

The **find ordered** operation retrieves all the records in the file in some
specified order

### Reorganize

The **reorganize** operation start the reorganization process
