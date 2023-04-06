# SQL
- [DDL (Data Definition Language)](#ddl-data-definition-language)
    - [CREATE](#create)
    - [ALTER](#alter)
    - [DROP](#drop)
- [DML (Data Manipulation Language)](#dml-data-manipulation-language)
    - [QUERY](#query)
    - [SELECT](#select)
    - [UNION](#union)
    - [EXCEPT](#except)
    - [INTERSECT](#intersect)
    - [Nested Queries](#nested-queries)
        - [IN & NOT IN](#in)
        - [EXISTS & NOT EXISTS](#exists--not-exists)
        - [With correlation](#with-correlation)
        - [UNIQUE & NOT UNIQUE](#unique)
        - [ANY & ALL](#any--all)
    - [EXCEPT](#except)
    - [DIVISION](#division)
    - [Aggregate Operators](#aggregate-operators)
        - [COUNT](#count)
        - [SUM](#sum)
        - [AVG](#avg)
        - [MIN & MAX](#min--max)
    - [GROUP BY](#group-by)
        - [HAVING](#having)
    - [Null Values](#null-values)
        - [3-valued logic](#3-valued-logic)
        - [Handling Null Values in SQL Operations](#handling-null-values-in-sql-operations)
        - [Left Outer Join](#left-outer-join)
        - [Right Outer Join](#right-outer-join)
        - [Full Outer Join](#full-outer-join)


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

<br>
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

<br>
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


<br>
<p id="query"></p>

- `QUERY`  
In SQL, there is a specific order in which the keywords in a query must appear. This order is as follows:  
`SELECT`: specify which columns to retrieve from the table(s).  
`FROM`: specify the table(s) from which to retrieve the data.  
`JOIN`: join other tables to the main table(s).  
`WHERE`: filter the rows to include in the results.  
`GROUP` BY: group the results by one or more columns.  
`HAVING`: filter the groups to include in the results.  
`ORDER BY`: sort the results.  
`LIMIT`: limit the number of rows returned.


<br>
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

<br>
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

***NOTE***: WE can have nested queries in the FROM clause.

```sql
SELECT Temp.rating, Temp.average
FROM (SELECT S.rating, AVG (S.age) AS average
      FROM SailorsS
      GROUP BY S.rating) AS Temp
WHERE Temp.average = (SELECT MIN (Temp.average)
                      FROM Temp)

-- Find those ratings for which the average age is the minimum over all ratings
```

<br>
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

<br>
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


<br>
<p id="nested-queries"></p>

- `Nested Queries`  
in general, a subquery must be recompiled for every row of the outer query.
    
```sql
SELECT S.sid
FROM Sailors S
WHERE S.rating = (SELECT MAX(S1.rating)
                  FROM Sailors S1);
```

<br>
<p id="in"></p>

- `IN & NOT IN`  
`IN`: returns true if the value _exists_ in the subquery.  
`NOT IN`: returns true if the value _does not exist_ in the subquery.

_example_:
```sql
SELECT S.sid -- IN keyword
FROM Sailors S
WHERE S.name IN ('Alice', 'Bob', 'Charlie');
```


<br>
<p id="exists--not-exists"></p>

- `EXISTS & NOT EXISTS`  
`EXISTS`: returns true if the subquery is _not empty_.  
`NOT EXISTS`: returns true if the subquery is _empty_.   

_example_:
```sql
SELECT S.name -- EXISTS keyword
FROM Sailors S
WHERE EXISTS (SELECT *
              FROM Reserves R
              WHERE R.sid = S.sid AND R.day = '10-10-10');
```


<br>
<p id="with-correlation"></p>

- `With correlation`  
in above example, the subquery is correlated with the outer query, because the subquery uses a variable from the outer query.


<br>
<p id="unique"></p>

- `UNIQUE & NOT UNIQUE`  
`UNIQUE`: returns true if the subquery returns _every row_ in the outer query _at most once_.  
`NOT UNIQUE`: returns true if the subquery returns _every row_ in the outer query _more than once_(there is at least one duplicate).

```sql
SELECT S.sid
FROM Sailors S
WHERE UNIQUE (SELECT R.sid
              FROM Reserves R
              WHERE R.bid = 103 AND S.sid = R.sid);
-- finds sailors with at most one reservation for boat #103.
```

<br>
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


<br>
<p id="EXCEPT"></p>

- `EXCEPT`  
`EXCEPT` returns the rows in the first query that are not in the second query.

```sql
SELECT S.sid
FROM Sailors S
WHERE S.rating > 7
EXCEPT
SELECT S.sid
FROM Sailors S
WHERE S.age > 30;
```

<br>
<p id="DIVISION"></p>

- `DIVISION`
There isn't a division operator in SQL. We should use some tricks to do division.


```sql
SELECT S.name -- First Method
FROM Sailors S
WHERE NOT EXISTS (SELECT B.bid
                  FROM Boats B

                  EXCEPT

                  SELECT R.bid
                  FROM Reserves R
                  WHERE R.sid = S.sid);
                  )

SELECT S.name -- Second Method
FROM Sailors S
WHERE NOT EXISTS (SELECT B.bid
                  FROM Boats B
                  WHERE NOT EXISTS (SELECT R.bid
                                    FROM Reserves R
                                    WHERE R.sid = S.sid AND R.bid = B.bid));
```
-- Find sailors who’ve reserved all boats.
```

<!-- ch5-part2.mp4 -->

<br>
<p id="aggregate-operators"></p>

- `Aggregate Operators`  
Aggregate operators are used to compute a single value from a set of values.

<br>
<p id="count"></p>

- `COUNT`  
COUNT(*) returns the number of rows in the table.  
COUNT(column) returns the number of non-null values in the column.  
COUNT(DISTINCT column) returns the number of distinct values in the column.
    
```sql
SELECT COUNT(*)
FROM Sailors;

SELECT COUNT(S.name)
FROM Sailors S;

SELECT COUNT(DISTINCT S.name)
FROM Sailors S;
```

<br>
<p id="sum"></p>

- `SUM`  
SUM(column) returns the sum of the values in the column.  
SUM(DISTINCT column) returns the sum of the distinct values in the column.

```sql
SELECT SUM(S.age)
FROM Sailors S;

SELECT SUM(DISTINCT S.age)
FROM Sailors S;
```

<br>
<p id="avg"></p>

- `AVG`  
AVG(column) returns the average of the values in the column.  
AVG(DISTINCT column) returns the average of the distinct values in the column.  

```sql
SELECT AVG(S.age)
FROM Sailors S;

SELECT AVG(DISTINCT S.age)
FROM Sailors S;
```

<br>
<p id="min--max"></p>

- `MIN & MAX`  
MIN(column) returns the minimum value in the column.
MAX(column) returns the maximum value in the column.

```sql
SELECT MIN(S.age)
FROM Sailors S;

SELECT MAX(S.age)
FROM Sailors S;
```

<br>
<p id="group-by"></p>

- `GROUP BY`  
GROUP BY is used to group the rows of a table into a set of summary rows.

```sql
SELECT S.rating, COUNT(*) AS num
FROM Sailors S
WHERE S.age > 30
GROUP BY S.rating;
```

***NOTE***: Column of aggregate operators doesn't have name. We can use `AS` to give it a name.  
***NOTE***: When we use `GROUP BY`, in `SELECT` clause, we can only use columns in `GROUP BY` clause or aggregate operators.  
***NOTE***: One answer tuple is generated per qualifying group.

<br>

***NOTE***: Conceptually, the `GROUP BY` operator works as follows:  
1. Cross-product of the tables in the `FROM` clause.
2. Apply the `WHERE` clause to the result of the cross-product.
3. Remove unwanted columns.
4. Group the remaining rows into groups, where two rows are in the same group if they have the same values in the columns in the `GROUP BY` clause.
5. For each group, compute the aggregate functions or expressions in the `HAVING` clause.


<br>
<p id="having"></p>

- `HAVING`  
HAVING is used to filter the groups generated by the GROUP BY clause.

```sql
SELECT S.rating, COUNT(*) AS num
FROM Sailors S
WHERE S.age > 30
GROUP BY S.rating
HAVING COUNT(*) > 1;

-- another example
SELECT S.rating, MIN (S.age)
FROM SailorsS
WHERE S.age>18
GROUP BY S.rating
HAVING 1 < (SELECT COUNT (*) 
            FROM SailorsS2
            WHERE S.rating=S2.rating)
```

***NOTE***: Attributes in group-qualification must be arguments
of an aggregate operation or must also appear in the grouping-list.
***NOTE***: HAVING clause can also contain a subquery.

<!-- ch5-part3 -->


<br>
<p id="null-values"></p>

- `Null Values`   
Fields in a table can be empty. These empty fields are called `NULL` values.


<br>
<p id="3-valued-logic"></p>

- `3-Valued Logic`

`AND` | T | F | NULL
--- | --- | --- | ---
T | T | F | NULL
F | F | F | F
NULL | NULL | F | NULL

`OR` | T | F | NULL
--- | --- | --- | ---
T | T | T | T
F | T | F | NULL
NULL | T | NULL | NULL


<br>
<p id="handling-null-values-in-sql-operations"></p>

- `Handling Null Values in SQL Operations`  
    - Comparisons *<, >, =* return null if one of their arguments in null.  
    - Arithmetic operations *+, -, *, /* return null if one of their arguments is null.  
    - *COUNT(*)* handles null values like other values (they get counted).
    - *COUNT(column)* ignores null values.
    - *COUNT, SUM, AVG, MIN, MAX* and variations using *DISTINCT* discard null values.
        - Special case: if one of *these operators, other than COUNT*, is applied to only null values, the result is null


<br>
<p id="left-outer-join"></p>

- `Left Outer Join`  
Left outer join returns all rows from the left table, and matching rows from the right table. The result is NULL from the right side, if there is no match.

```sql
SELECT S.sid, S.name, R.bid
FROM Sailors S LEFT OUTER JOIN Reserves R
ON S.sid = R.sid;
```

<br>
<p id="right-outer-join"></p>

- `Right Outer Join`  
Right outer join returns all rows from the right table, and matching rows from the left table. The result is NULL from the left side, if there is no match.

```sql
SELECT S.sid, S.name, R.bid
FROM Sailors S RIGHT OUTER JOIN Reserves R
ON S.sid = R.sid;
```

<br>
<p id="full-outer-join"></p>

- `Full Outer Join`  
Full outer join returns all rows from both tables. The result is NULL in both sides when there is no match.

```sql
SELECT S.sid, S.name, R.bid
FROM Sailors S FULL OUTER JOIN Reserves R
ON S.sid = R.sid;
```

<br>
