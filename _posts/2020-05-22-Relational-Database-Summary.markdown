---
layout: post
title: "Relational Database Short Summary"
date: 2020-05-22
description: Key concepts of relational database including common used terminologies and normal forms.
img:  rdb/workflow.jpg
---

Basic Terminologies
>#### What is a Database
A database is a set of data stored in a computer. This data is usually structured in a way that makes the data easily accessible.
> #### What is Relational Database
> A relational database is one type of database. It uses a structure that allows us to identify and access data in relation to another piece of data in the database. Often, data in a relational database is organized into tables.
> #### What is Table
> Table has columns and rows.
> #### What is RDBMS
> Relational Database Management System is a program that allows you to create, update, and administer a relational database.
> #### What is SQL
>  Structured query language is a programming language used to communicate with data stored in a RDBMS.
>  Many RDBMSs use SQL to access the data in tables.
>  What is SQLLite
>  It contains a minimal SQL commands which are the same across all RDBMSs.

### Data Relationships
A relationship between tables specifies the field/s which the 2 tables have in common. 
1. One-to-One
One man can only have one wife in most countries
2. One-to-Many
One man can have many wives in Iran.
3. Many-to-Many
One man can have many wives while one woman can have many husbands.
### Data Integrity
The accuracy and consistency of data
1. Entity integrity
No duplicate rows in a table.
2. Referential integrity
If two or more tables have a relationship. We have to ensure that the foreign key value matches the primary key value at all times.
3. Domain integrity 
The validity of entries for a given column.
The right data type.
The right constraints and rules to define the data format and/or restricting the range of possible values.
4. User-Defined integrity
Apply business rules to the database

### Keys
1. Primary key
consists of one or more columns whose data contained within are used to uniquely identify each row in the table. 
The columns must be unique and not NULL or blank.
2. Foreign key
A foreign key is a set of one or more columns in a table that refers to the primary key in another table. 
3. Candidate Key
a column, or set of columns, in a table that can uniquely identify any database record without referring to any other data. Each table may have one or more candidate keys, but one candidate key is unique, and it is called the primary key. 
4. Composite Key
A key composed of several columns

### Database Normalization
The process of structuring a relational database in accordance with a series of normal forms in order to reduce data redundancy and improve data integrity.

##### Data Redundancy
The same information appears in multiple places in the database
![image](../assets/img/rdb/1590171704427.png)

The columns **branch, hod, and office_tel** are the same for all the records. So these are data redundancy.
##### Insertion Anomaly
When one attribute cannot be inserted into the database without the presence of other attributes.
For example, we cannot add a new course unless we have at least one student enrolled on the course.
##### Update Anomaly
An attribute of a record is changed. This attribute is saved in multiple places. Then we have to make sure to change all the places.
For example, a teacher changes his/her name. We must make sure all the names are updated.
#####  Delete Anomaly
The inverse of insertion anomaly. If the presence attributes are deletes, the current attribute does not exist.
For example, if the only student in a course drops, the course should be deleted too.
##### Normal Forms
###### Dependency
###### Functional Dependency
A relationship between the primary key and other non-key attributes within a table.
###### Partial Dependency
An attribute in a table depends on only a part of the primary key and not on the whole key.

###### Solution
divide the table, remove the attribute which is causing partial dependency, and move it to some other table where it fits in well.
###### Transitive Dependency
A non-primary attribute depends on another non-primary attribute.
###### Solution
Create a new table for these attributes and add the primary key in their original table.
###### Multi-valued Dependency
For a dependency A->B(B depends on A), a single value of A, multiple value of B exists.
There are one-to-many relations within a table.
B does not depend on other columns except A
Cause repetition of data
###### Solution
Decomposite the table into two tables.
###### First Normal Form(1NF)
1. single valued attributes.
	Each column of your table should be single valued which means they should not contain multiple values.
	 ![image](../assets/img/rdb/1590173394243.png)
2. Values in a column should be in the same domain
3. All the columns in a table should have unique names
4. The order of the columns should not matter
###### Second Normal Form(2NF)
1. In 1NF 
2. Do not have partial dependency
**Non-primary attribute depend on part of primary key**
###### Third Normal Form(3NF)
1. In 2NF
2. Do not have Transitive Dependency
**Non-primary attribute depends on non-primary attribute**
###### Boyce and Codd Normal Form(BCNF/3.5NF)
1. In 3NF
2.  For any dependency A->B, A should be a super key.
A cannot be a non-prime attribute, if B is a primary attribute.
A primary attribute cannot depend one a non-primary attribute.
**primary attribute depends on non-primary attribute**
![image](../assets/img/rdb/1590174899370.png)
Primary key: student_id and subject
Subject depends on professor. Subject is primary key while professor is not.
###### 4NF
1. In BCNF
2. not have multi-valued dependency