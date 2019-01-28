* relational db : organize info in one or more tables
### or relation
* table : collection of data that organizes info into rows & columns
* column : set of data values of a  particular type
* row : single record in a table
## Data
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
* create table : is a clause. Perform specific task. CAPITAL LETTERS. or
  Command.
* table_name : name of the table 
* `(column (data_type; ...)` : parameter. Lise of columns, data types or
  values that are passed to a clause as an argument.
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
