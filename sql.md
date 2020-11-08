* relational db : organize info in one or more tables
* Four basic operation : 
    * INSERT
    * SELECT : extract information from a table
        * SELECT *columns* FROM *table* (WHERE *condition*) (ORDER BY *column*)
    * UPDATE
    * DELETE
Functions to perform calculations : 
* AVG
* COUNT
* DISTINCT, for getting distinct values without duplicates
* MAX
* MIN
## Operations
* WHERE, matching on some strict condition
* LIKE, matching on substrings for text
* LIMIT
* GROUP BY
* ORDER BY
* JOIN, combining data from multiple tables

### or relation
* table : collection of data that organizes info into rows & columns
* column : set of data values of a  particular type
* row : single record in a table
## Data
* BLOB, for “binary large object”, raw binary data that might represent files

INTEGER
* int
* smallint : 32bits
* integer : 64 bits
* tinyint
* mediumint
* bigint : fewer than both of those

NUMERIC
* boolean
* date
* datetime
* `numeric(scale,precision),` which solves floating-point imprecision by using as many bits as needed, for each digit before and after the decimal point
* time
* timestamp

REAL
* decimal:
* real, for floating-point values : 32 bits
* double precision, with more bits : 64 bits

TEXT
* char(n), for an exact number of characters
* varchar(n), for a variable number of characters, up to a certain limit
* text

* integer (entier)
* text : text strign
* date : yyyy-mm-dd
* real : decimal value
* a statement : text that the db recognize as a valid command. ;
```sql
CREATE TABLE table_name (
  column_1 data_type,
  column_2 data_type,
  column_3 data_type
  );
```
* create table : is a clause. Perform specific task. CAPITAL LETTERS. or Command.
* table_name : name of the table 
* `(column (data_type; ...)` : parameter. Lise of columns, data types or values that are passed to a clause as an argument.
```sql
INSERT INTO row (column, column, column) (c'est un paramètre)
VALUES (c'est une clause) (1, 'Name', 2);
SELECT *FROM tables
SELECT name FROM table;
```
  * returns all data in the name column of the table
  * Select : clause that indicates that the statement is a query
  * \* : select every column in a table
* SELECT statements always return a new table called the result set
```sql
UPDATE table
SET column =xx
WHERE = row = 1;
```
* ALTER TABLE : statement adds a new column
```sql
ALTER TABLE celebs
ADD COLUMN twitter_handle TEXT;
```
```sql
DELETE FROM celebs
WHERE column IS NULL;
```
* IS NULL : condition
# Constraints
* PRIMARY KEY : columns to uniquely identify the rows. PAS DE DOUBLON
* UNIQUE : different value for every row. Many different unique columns.
* DEFAULT
```sql
CREATE TABLE celebs (
id INTEGER PRIMARY KEY,
name TEXT UNIQUE,
date TEXT NO NULL,
death, TEXT DEFAULT 'not applicable',
);
```
