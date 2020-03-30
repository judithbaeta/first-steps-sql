# first-steps
My first ever project.

Hi there!

Judith here, I have been wanting to learn programming for a while and now that I'm in isolation due to #covid-19 pandemic/crisis I thought it would be a good time to get to it. Jokes on me, I just quit my FT job and was supposed to be travelling aroud the SE Asia but instead here I am. 

I'm interested in becoming a data scientist and this should be fun!

-------------------------------------------------------------------------------------------------------

## Project 1// MANIPULATION

### 1 - CREATE TABLE
The 'CREATE TABLE' statement creates a new table in a database. It allows one to specify the name of the table and the name of each column in the table.

```
 CREATE TABLE table_name (
  column1 datatype,
  column2 datatype,
  column3 datatype
);
```
valid data types:
1. 'INTEGER' a whole number
2. 'TEXT' a text string
3. 'DATE' a date (format is YYYY-MM-DD)
4. 'REAL' a decimal number

### 2- INSERT
The 'INSERT INTO' statement is used to add a new record (row) to a table.

```
-- Insert into columns in order:
INSERT INTO table_name
VALUES (value1, value2);
```

```
-- Insert into columns by name:
INSERT INTO table_name (column1, column2)
VALUES (value1, value2);
```

### 3 - UPDATE
The 'UPDATE' statement is used to edit records (rows) in a table. It includes a 'SET' clause that indicates the column to edit and a 'WHERE' clause for specifying the record(s).

```
UPDATE table_name
SET column1 = value1, column2 = value2
WHERE some_column = some_value;
```

### 4- ALTER TABLE
The 'ALTER TABLE' statement is used to modify the columns of an existing table. When combined with the 'ADD COLUMN' clause, it is used to add a new column.

```
ALTER TABLE table_name
ADD column_name datatype;
```

### 5- DELETE
The 'DELETE' statement is used to delete records (rows) in a table. The 'WHERE' clause specifies which record or records that should be deleted. If the WHERE clause is omitted, all records will be deleted.

```
DELETE FROM table_name
WHERE some_column = some_value;
```

### 6 - Column Constraints
Column constraints are the rules applied to the values of individual columns:
  'PRIMARY KEY' constraint can be used to uniquely identify the row.
  'UNIQUE' columns have a different value for every row.
  'NOT NULL' columns must have a value.
  'DEFAULT' assigns a default value for the column when no value is specified.
  
 There can be only one PRIMARY KEY column per table and multiple UNIQUE columns.

```
CREATE TABLE student (
  id INTEGER PRIMARY KEY,
  name TEXT UNIQUE,
  grade INTEGER NOT NULL,
  age INTEGER DEFAULT 10
);
```

### Further Resources and References
[SQL Compiler](https://www.db-fiddle.com/) and make sure the top tab has "MySQL 5.7".
[SQLite](https://www.codecademy.com/courses/learn-sql/articles/what-is-sqlite) and [SQLite Data Starter Packs](http://2016.padjo.org/tutorials/sqlite-data-starterpacks/#toc-american-community-survey-1-year-data-for-2015)
[Cheatsheet](https://www.codecademy.com/learn/learn-sql/modules/learn-sql-manipulation/cheatsheet)

----------------------------------------------------------------------------------------------------

## Project 2// QUERIES

### 1- SELECT Statement
The ```SELECT *``` statement returns all columns from the provided table in the result set. The given query will fetch all columns and records (rows) from the ```movies``` table.

```
SELECT *
FROM movies;
```

### 2- AS Clause
Columns or tables in SQL can be aliased using the ```AS``` clause. This allows columns or tables to be specifically renamed in the returned result set. The given query will return a result set with the column for name renamed to ```movie_title```.

```
SELECT name AS 'movie_title'
FROM movies;
```

### 3- DISTINCT Clause
Unique values of a column can be selected using a ```DISTINCT``` query. For a table ```contact_details``` having five rows in which the ```city``` column contains Chicago, Madison, Boston, Madison, and Denver

```
SELECT DISTINCT city
FROM contact_details;
```

### 4- WHERE Clause
The ```WHERE``` clause is used to filter records (rows) that match a certain condition. The given query will select all records where the ```pub_year```equals ```2017```.

```
SELECT title
FROM library
WHERE pub_year = 2017;
```

### 5- LIKE Operator
The ```LIKE``` operator can be used inside of a ```WHERE``` clause to match a specified pattern. The given query will match any movie that begins with Star in its title.

```
SELECT name
FROM movies
WHERE name LIKE 'Star%';
```

> The ```_``` wildcard can be used in a LIKE operator pattern to match any single unspecified character. The given query will match any movie which begins with a single character, followed by ove.

```
SELECT name
FROM movies
WHERE name LIKE '_ove';
```
> The ```%``` wildcard can be used in a LIKE operator pattern to match zero or more unspecified character(s). The example query will match any movie that begins with The, followed by zero or more of any characters.

```
SELECT name
FROM movies
WHERE name LIKE 'The%';
```

### 6- BTWEEN Operator
The ```BETWEEN``` operator can be used to filter by a range of values. The range of values can be text, numbers or date data. The given query will match any movie made between the years 1980 and 1990, inclusive.

```
SELECT *
FROM movies
WHERE year BETWEEN 1980 AND 1990;
```

### 7- AND Operator
The ```AND``` operator allows multiple conditions to be combined. Records must match both conditions that are joined by AND to be included in the result set. The example query will match any car that is blue and made after 2014.

```
SELECT model 
FROM cars 
WHERE color = 'blue' 
  AND year > 2014;
```

### 8- OR Operator
The ```OR``` operator allows multiple conditions to be combined. Records matching either condition joined by the OR are included in the result set. The given query will match customers whose state is either ca or ny.

```
SELECT name
FROM customers 
WHERE state = "ca" 
   OR state = "ny";
```

### 9- NULL Values
Column values in SQL records can be ```NULL```, or have no value. These records can be matched (or not matched) using the ```IS NULL``` and ```IS NOT NULL``` operators in combination with the ```WHERE``` clause. The given query will match all addresses where the address has a value or is not NULL.

```
SELECT address
FROM records
WHERE address IS NOT NULL;
```

### 10- ORDER BY Clause
The ```ORDER BY``` clause can be used to sort the result set by a particular column either alphabetically or numerically. It can be ordered in ascending (default) or descending order with ```ASC/DESC```. In the example, all the rows of the contacts table will be ordered by the birth_date column in descending order.

> Alphabetically, A-Z = DESC and Z-A is ASC

```
SELECT *
FROM contacts
ORDER BY birth_date DESC;
```

### 11- LIMIT Clause
The ```LIMIT``` clause is used to narrow, or limit, a result set to the specified number of rows. The given query will limit the result set to 5 rows.

```
SELECT *
FROM movies
LIMIT 5;
```
