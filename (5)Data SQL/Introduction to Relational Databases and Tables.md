---
module:2
tags: SQL
typora-copy-images-to: ./attachments
---

# Introduction to Relational Databases and Tables

## Relational Database Concepts

### Relational Model

- Most used data model
- Allows for **data independence**
- Data is stored in a table

### Entity-Relationship Model

- Used as a tool to design relational databases

![image-20230705221626956](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230705_1688591788.png)

### Primary Keys and Foreign Keys

![image-20230705223028836](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230705_1688592630.png)

### Summary

- The key advantage of the relational model is data independence
- Entities are independent objects which have attributes
- Entities map to Tables in a Relational Database
- Attributes map to Columns in a Table
- Common data types include characters, numbers, and dates/times.



## Types of SQL Statements

- **Types**:
  - Data Definition Language statements
  - Data Manipulation Language statements
- **DDL** (Data, Definition, Language) statements:
  - Define, change or drop data
  - **Common DDL**:
    - CREATE
    - ALTER
    - TRUNCATE
    - DROP
- **Data Manipulate Language Statements**:
  - Read and modify data
  - CRUD operations (CREATE, Read, Update & Delete rows)
  - Common DML:
    - INSERT
    - SELECT
    - UPDATE
    - DELETE



## CREATE TABLE

```sql
CREATE TABLE table_name
(
	column_name_1 datatype optional_parameters,
	column_name_2 datatype,
	...
	column_name_n datatype
)
```

**Example**:

- Create a table for Canadian provinces:

  ```sql
  CREATE TABLE provinces(
  	id char(2) PRIMARY KEY NOT NULL,
  	name varchar(24)
  )
  ```

  <img src="https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230706_1688632353.png" alt="image-20230706093231933" style="zoom:50%;" />



## ALTER, DROP, TRUNCATE

### ALTER TABLE ... ADD COLUMN

- Add or remove columns

  ```sql
  ALTER TABLE <table_name>
  	ADD COLUMN <column_name_1> datatype
  	...
  	ADD COLUMN <column_name_n> datatype;
  ```

- Modify the data type of columns

  ```sql
  ALTER TABLE <table_name>
  	ALTER COLUMN <column_name> SET DATA TYPE
  <datatype>;
  ```

  ![image-20230706093846719](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230706_1688632727.png)

- Add or remove keys

  ```sql
  ALTER TABLE author
  	DROP COLUMN telephone_number;
  ```

- Add or remove constriants

- Rename Columns

  ```sql
  ALTER TABLE table_name
  RENAME COLUMN
  current_column_name T0
  new_column_name;
  ```

  

### DROP TABLE

```sql
DROP TABLE <table_name>
```



### TRUNCATE TABLE

```sql
TRUNCATE TABLE <table_name>
	IMMEDIATE;
```

![image-20230706094755045](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230706_1688633276.png)
