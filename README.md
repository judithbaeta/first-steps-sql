# first-steps
My first ever project.

Hi there!

Judith here, I have been wanting to learn programming for a while and now that I'm in isolation due to #covid-19 pandemic/crisis I thought it would be a good time to get to it. Jokes on me, I just quit my FT job and was supposed to be travelling aroud the SE Asia but instead here I am. 

I'm interested in becoming a data scientist and this should be fun!

-------------------------------------------------------------------------------------------------------

# Project 1 · MANIPULATION

**1 - CREATE TABLE

The 'CREATE TABLE' statement creates a new table in a database. It allows one to specify the name of the table and the name of each column in the table.

 CREATE TABLE table_name (
  column1 datatype,
  column2 datatype,
  column3 datatype
);

**2- INSERT

The 'INSERT INTO' statement is used to add a new record (row) to a table.

-- Insert into columns in order:
INSERT INTO table_name
VALUES (value1, value2);

-- Insert into columns by name:
INSERT INTO table_name (column1, column2)
VALUES (value1, value2);

**3 - UPDATE

The 'UPDATE' statement is used to edit records (rows) in a table. It includes a 'SET' clause that indicates the column to edit and a 'WHERE' clause for specifying the record(s).

UPDATE table_name
SET column1 = value1, column2 = value2
WHERE some_column = some_value;

**4- ALTER TABLE

The 'ALTER TABLE' statement is used to modify the columns of an existing table. When combined with the 'ADD COLUMN' clause, it is used to add a new column.

ALTER TABLE table_name
ADD column_name datatype;

**5- DELETE

The 'DELETE' statement is used to delete records (rows) in a table. The 'WHERE' clause specifies which record or records that should be deleted. If the WHERE clause is omitted, all records will be deleted.

DELETE FROM table_name
WHERE some_column = some_value;

**6 - Column Constraints

Column constraints are the rules applied to the values of individual columns:
  'PRIMARY KEY' constraint can be used to uniquely identify the row.
  'UNIQUE' columns have a different value for every row.
  'NOT NULL' columns must have a value.
  'DEFAULT' assigns a default value for the column when no value is specified.
  
 There can be only one PRIMARY KEY column per table and multiple UNIQUE columns.

CREATE TABLE student (
  id INTEGER PRIMARY KEY,
  name TEXT UNIQUE,
  grade INTEGER NOT NULL,
  age INTEGER DEFAULT 10
);

----------------------------------------------------------------------------------------------------

