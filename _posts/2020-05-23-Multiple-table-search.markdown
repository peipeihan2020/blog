---
layout: post
title: "Data Query Lanage(DQL): Multiple Table Search-Join && Union"
date: 2020-05-24
description: Combine search from multiple tables.
img: 
---

#### JOIN
Combine rows from two or more tables
```
SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate
FROM Orders
INNER JOIN Customers ON Orders.CustomerID=Customers.CustomerID;
```
1. Inner Join
return records that have matching values in both tables
A union B
2. Left Join
return all records from the left table, and the matched records from the right table
A
3. Right Join
return all records from the right table and the matched records from the left table
B
4. FULL Join
return all records when there is a match in either left or right table
AUB

![image](../assets/img/ssearch/1590240564150.png)

#### UNION
Combine result from multiple SELECT statements
1. Each SELECT statement must have same account of columns
2. The columns must also have similiar data types.
3. The columns in each SELECT statement must also be in the same order 
``` 
SELECT 'Customer' As Type, ContactName, City, Country
FROM Customers
UNION
SELECT 'Supplier', ContactName, City, Country
FROM Suppliers;
```