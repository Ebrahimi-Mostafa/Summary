# SQL
- [DDL (Data Definition Language)](#ddl-data-definition-language)
    - [CREATE](#create)
    - [ALTER](#alter)
    - [DROP](#drop)
- [DML (Data Manipulation Language)](#dml-data-manipulation-language)

<!-- ch5-part1.mp4 -->

## `DDL (Data Definition Language)`
<p id="create"></p>

- `CREATE`   
```sql
CREATE TABLE table_name (
    column1 datatype,
    column2 datatype,
    column3 datatype,
   ....
);
```
_example_:
```sql
CREATE TABLE Sailors (
    sid integer,
    sname string,
    rating integer,
    age real
);
```

<p id="alter"></p>

- `ALTER`
```sql
ALTER TABLE table_name
ADD column_name datatype;
```
_example_:
```sql
ALTER TABLE Sailors
ADD address string;
```

<p id="drop"></p>

- `DROP`
```sql
DROP TABLE table_name;
```
_example_:
```sql
DROP TABLE Sailors;
```


---
## `DML (Data Manipulation Language)`

We use these tables for executing queries on the database.

    Sailors (sid: integer, sname: string, rating: integer, age: real)      
    Boats (bid: integer, bname: string, color: string)  
    Reserves (sid: integer, bid: integer, day: date)

- `SELECT`
```sql
SELECT [DISTINCT] col1, col2, ...  
FROM table_name;
WHERE condition; -- optional
```
***Note***: SELECT `*` selects every column in the table.  
***Note***: SELECT `DISTINCT` selects only unique values.

_example_:
```sql
SELECT S.sname, R.bid, R.day
FROM Sailors S, Reserves R
WHERE S.sid = R.sid AND S.rating > 7;
```