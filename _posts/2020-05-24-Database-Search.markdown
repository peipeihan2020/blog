---
layout: post
title: "Data Query Lanage(DQL): Single Table Search"
date: 2020-05-23
description: Most basic statements for single table search.
img: 
---

#### SELECT

```
SELECT column1, column2, ...
FROM table_name;

SELECT * FROM table_name;
```
##### Alias

```
SELECT * FROM table_name AS alias;
```

##### Select Non duplicated results

```
SELECT DINSTINC * FROM table_name;
```

##### Select top count results

```
SELECT TOP count * FROM table_name;
```

##### Select by order
###### Ascending
```
    SELECT * FROM table_name order by column_name;
```
###### Descending
```
    SELECT * FROM table_name order by column_name DESC;
```

##### Select statistic results
###### Min

```
SELECT MIN(column_name) FROM table_name;
```
###### Max

```
SELECT MAX(column_name) FROM table_name;
```
###### Count

```
SELECT COUNT(column_name) FROM table_name;
```
###### Average

```
SELECT AVG(column_name) FROM table_name;
```
###### Sum

```
SELECT SUM(column_name) FROM table_name;
```
###### Group
Group rows with same value into  summary rows

```
SELECT column_name(s) FROM table_name 
GROUP BY column_name(s)
```
#### Filter Records
###### Where
Apply filter conditions to the Select statments
###### Logical Operators

![image](../assets/img/ssearch/1590320939538.png)

###### Comparison Operators
![image](../assets/img/ssearch/1590320894286.png)

###### Null check

```
SELECT column_names
FROM table_name
WHERE column_name IS NULL;

SELECT column_names
FROM table_name
WHERE column_name IS NOT NULL;
```

###### Pattern Select: Like
![image](../assets/img/ssearch/1590321303809.png)
![image](../assets/img/ssearch/1590321344511.png)

###### Aggregate condition: Having
HAVING usually appears with GROUP BY
```
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s);
```
###### Switch Case in SQL
Check conditions and return results from the first meet condition
```
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
END;

SELECT OrderID, Quantity,
CASE
    WHEN Quantity > 30 THEN 'The quantity is greater than 30'
    WHEN Quantity = 30 THEN 'The quantity is 30'
    ELSE 'The quantity is under 30'
END AS QuantityText
FROM OrderDetails;
```

