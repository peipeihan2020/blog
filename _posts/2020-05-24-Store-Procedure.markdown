---
layout: post
title: "Store Procedure"
date: 2020-05-23
description: Saved SQL commands.
img: 
---

Pre-Prepared SQL statements that can be reused.

```
CREATE PROCEDURE procedure_name
AS
sql_statement
GO;
```
Execute 

```
EXEC procedure_name;
```
With parameter

```
CREATE PROCEDURE SelectAllCustomers @City nvarchar(30), @PostalCode nvarchar(10)
AS
SELECT * FROM Customers WHERE City = @City AND PostalCode = @PostalCode
GO;
```