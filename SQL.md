# SQL
- [DDL (Data Definition Language)](#ddl-data-definition-language)
    - [CREATE](#create)
    - [ALTER](#alter)
    - [DROP](#drop)
- [DML (Data Manipulation Language)](#dml-data-manipulation-language)
    - [SELECT](#select)
    - [UNION](#union)
    - [EXCEPT](#except)
    - [INTERSECT](#intersect)
    - [Nested Queries](#nested-queries)
        - [IN & NOT IN](#in)
        - [ANY & ALL](#any--all)

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

<p id="select"></p>

- `SELECT`
```sql
SELECT [DISTINCT] col1, col2, ...  
FROM table_name;
WHERE condition; -- optional
```
***NOTE***: SELECT `*` selects every column in the table.  
***NOTE***: SELECT `DISTINCT` selects only unique values.

_example_:
```sql
SELECT S.sname, R.bid, R.day
FROM Sailors S, Reserves R
WHERE S.sid = R.sid AND S.rating > 7;
```

***NOTE***: We can have expressions in the SELECT clause.  
***NOTE***: `AS` and `=` are two ways to rename a column.

_example_:
```sql
SELECT 2*S.rating AS rate1, rate2 = S.rating / 2
FROM Sailors S;
```

***NOTE***: `LIKE` is used to match a pattern.  
***NOTE***: `_` matches any single character and `%` matches 0 or more characters.

_example_:
```sql
SELECT S.sname
FROM Sailors S
WHERE S.sname LIKE 'B_%B';
```

<p id="union"></p>

- `UNION`

```sql
SELECT S.sid
FROM Sailors S, Reserves R, Boats B
WHERE S.sid = R.sid AND R.bid = B.bid AND B.color = 'red'
UNION
SELECT S.sid
FROM Sailors S, Reserves R, Boats B
WHERE S.sid = R.sid AND R.bid = B.bid AND B.color = 'green';
```

***NOTE***: `UNION` deletes duplicate rows. We can use `UNION ALL` to keep duplicates.


<p id="except"></p>

- `EXCEPT`

```sql
SELECT S.sid
FROM Sailors S, Reserves R, Boats B
WHERE S.sid = R.sid AND R.bid = B.bid AND B.color = 'red'
EXCEPT
SELECT S.sid
FROM Sailors S, Reserves R, Boats B
WHERE S.sid = R.sid AND R.bid = B.bid AND B.color = 'green';
```

***NOTE***: `EXCEPT` deletes duplicate rows. We can use `EXCEPT ALL` to keep duplicates.

<p id="intersect"></p>

- `INTERSECT`

```sql
SELECT S.sid
FROM Sailors S, Reserves R, Boats B
WHERE S.sid = R.sid AND R.bid = B.bid AND B.color = 'red'
INTERSECT
SELECT S.sid
FROM Sailors S, Reserves R, Boats B
WHERE S.sid = R.sid AND R.bid = B.bid AND B.color = 'green';
```

***NOTE***: `INTERSECT` deletes duplicate rows. We can use `INTERSECT ALL` to keep duplicates.


<p id="nested-queries"></p>

- `Nested Queries`
    
```sql
SELECT S.sid
FROM Sailors S
WHERE S.rating = (SELECT MAX(S1.rating)
                  FROM Sailors S1);
```

<p id="in"></p>

- `IN & NOT IN`

_example_:
```sql
SELECT S.sid -- IN keyword
FROM Sailors S
WHERE S.name IN ('Alice', 'Bob', 'Charlie');
```


<p id="any--all"></p>

- `ANY & ALL`  
`ALL`: returns true if the comparison is true for _all_ rows in the subquery.  
`ANY`: returns true if the comparison is true for any row(_at least one row_) in the subquery.


```sql
SELECT S.name -- ALL keyword
FROM Sailors S
WHERE S.rating > ALL (SELECT S1.rating
                      FROM Sailors S1
                      WHERE S1.age > 30);

SELECT S.name -- ANY keyword
FROM Sailors S
WHERE S.rating > ANY (SELECT S1.rating
                      FROM Sailors S1
                      WHERE S1.age > 30);
```
