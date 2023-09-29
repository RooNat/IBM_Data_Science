---
module:1
tags: SQL
typora-copy-images-to: ./attachments
---

# Get Started with SQL

[toc]

**DBMS**: Database Management System - software to manage database 

**RDBMS**: Relational database management system

**Basic SQL Commands:**

1. Create a table
2. Insert
3. Select
4. Update
5. Delete



## SELECT statement

> Retrieving data from a table

### Retrieving rows from a table

- After creating a table and inserting data into the table, we want to see the data

- **SELECT statement**

  - A Data Manipulation Language(DML) statement is used to read and modify the data
  - **Select statement**: <u>Query</u> 
  - **Result from the query**: <u>Result set/table</u>

  ```sql
  Select * from <tablename>
  ```

### Retrieving a subset of the columns

- You can retrieve just the columns you want

- The order of the columns displayed always matches the order in the SELECT statement.

  ```SQL
  SELECT <column 1>, <column 2> from Book
  ```

### Restricting the Result Set: WHERE Clause

- Restricts the result set

- Always requires a Predicate:

  ```sql
  Select book_id, title from Book Where predicate
  ```

  - Evaluates to:
    - True, False or Unknown
    - Used in the search condition of the `where` clause

  ```sql
  select book_id, title from Book where book_id='B1'
  ```

<img src="https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230704_1688486011.png" alt="image-20230704165329475" style="zoom:50%;" />

---

## COUNT, DISTINCT, LIMIT

### COUNT

> a built-in function that retrieves **the number of rows** matching the query criteria

- number of rows in a table:

  ```sql
  select COUNT(*) from <tablename>
  ```

- Rows in the MEDALs table where Country is Canada:

  ```sql
  select COUNT(COUNTRY) from MEDALS where COUNTRY='CANADA' 
  ```

### DISTINCT

> DISTINCT is used to remove duplicate values from a result set.

- Retrieve unique values in a column:

  ```sql
  select DISTINCT columnname from <tablename>
  ```

- List of unique countries that received GOLD medals:

  ```sql
  select DISTINCT COUNTRY from MEDALS where MEDALTYPE='GOLD'
  ```

### LIMIT

> LIMIT is used for restricting the number of rows retrieved from the database

- Retrieve just the first 10 rows in a table:

  ```sql
  select * from tablename LIMIT 10
  ```

- Retrieve 5 rows in the MEDALS table for a particular year:

  ```sql
  select * from MEDALS where YEAR=2018 LIMIT 5
  ```

## INSERT

### Add rows to a table

- Create the table (`CREATE TABLE` statement)
- Populate table with data:
  - `INSERT` statement
    - A Data Manipulation Language(DML) statement used to read and modify data

```sql
INSERT INTO [TableName] <([ColumnName],...)> VALUES ([Value],...)
```

- One row at a time or multiple rows



## UPDATE and DELETE

### UPDATE

> A Data Manipulation Language(DML) statement used to read and modify data

```sql
UPDATE [TableName] SET [[ColumnName]=[Value]] WHERE <[Condition]>
```



### DELETE

```sql
DELETE FROM [TableName] WHERE <[Condition]>
```

