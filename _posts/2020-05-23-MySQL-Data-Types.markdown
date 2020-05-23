---
layout: post
title: "MySQL Data Types"
date: 2020-05-23
description: string, numeric, date and time.
img: 
---


#### String Types
1. CHAR(size)
letters, numbers and special characters
fixed length
size: from 0 to 255, default 1
2. VARCHAR(size)
letters, numbers and special characters
variable length
size: maximal length, 0-65535 
3. BINDARY(size)
binary byte
fixed length
size: column length, default to 1
4. VARBINARY(size)
binary byte
variable length
size: maximum length
5. TINYBLOB
BLOBs(Binary Large Objects)
max length: 255 bytes
6. TINYTEXT
String with maximum length 255
7. TEXT(size)
string with maximum 65535
8. BLOB(size)
BLOBs up to 65535 bytes
9. MEDIUMTEXT
<=4,294,967,295 characters
10. MEDIUMBLOB
<=16,777,215 bytes
11. LONGTEXT
 maximum 4,294,967,295
12. LONGBLOB
 maximum 4,294,967,295 bytes  
13. ENUM
 the list can contain 65535 values
 If a value is not in the list, a blank value will be inserted
14. SET
 64 values list
 
#### Numeric Data Types:

 option:
 UNSIGNED: disallow negative values
 ZEROFILL: Automatically adds UNSIGNED to the column
 
 1. BIT(size)
 bit-value type
 1 to 64, default 1
 2. TINYBIT(size)
 -128 to 127 or 0 to 255
 size: the maximum display width
 3. BOOL/BOOLEAN
 4. SMALLINT(size)
 5. MEDIUMINT(size)
 6. INT/INTEGER(size)
 7. BIGINT(size)
 8. FLOAT(size, d)
 d: precision
 9. FLOAT(p)
 p: wheather to use FLOAT or DOUBLE
 P:0-24, FLOAT()
 P:25-53: DOUBLE()
 10. DOUBLE(size, d)
 11. DECIMAL/DEC(size, d)

#### Date and Time
1. DATE
format: YYYY-MM-DD
2. DATETIME(fsp)
a date and time combination
YYYY-MM-DD hh:mm:ss
DEFAULT and ON UPDATE: get initialization and updating to the current datetime
3. TIMESTAMP(fsp)
the number of seconds since the Unix epoch(1970-01-01 00:00:00 UTC)
YYYY-MM-DD hh:mm:ss
DEFAULT CURRENT_TIMESTAMP and ON UPDATE CURRENT_TIMESTAMP: current date and time
4. TIME(fsp)
hh:mm:ss
5. YEAR 