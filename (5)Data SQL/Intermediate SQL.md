---
module:3
tags: SQL
typora-copy-images-to: ./attachments
---

# Intermediate SQL

[toc]

## Using String Patterns and Ranges

> ***Objectives***: Describe how to simplify a SELECT statement by using:
>
> - String patterns
> - Ranges, or
> - Sets of values

- `WHERE` requires a predicate
- A predicate is an expression that evaluates to `TURE`, `FALSE`, or `UNKNOWN`
- Use the `LIKE` predicate with string patterns for the search

**Example**:

```sql
WHERE <columnname> LIKE <string pattern>
```

```sql
WHERE <columnname> IN ('AU','BR')
```

```sql
WHERE <columnname> BETWEEN 20 AND 200
```



## Sorting Result Sets

> ***Objectives:*** 
>
> - Describe how to sort the result set by either ascending or descending order
> - Explain how to indicate which column to use for the sorting order

### Using the ORDER BY clause

- Example:

```sql
select title from Book order by title
```

- Specifying Column Sequence Number:

  ```sql
  select title, pages from Book ORDER BY 2
  ```

## Grouping Result Sets

- Eliminating Duplicates - `DISTINCT` Clause

  ```sql
  select distinct(country) from Author
  ```

- `GROUP BY` clause

  ```sql
  select country, count(country) from Author GROUP BY country
  ```

- `Having` clause

  ```sql
  select country, count(country) as Count from Author group by country having count(country)>4
  ```

  

## Built-in Database Functions

> ***Characters:***
>
> - Most databases come with built-in SQL functions
> - Built-in functions can be included as part of SQL statements
> - Database functions can significantly reduce the amount of data that needs to be retrieved
> - Can speed up data processing

### Aggregate or Column Functions

- INPUT: Collection of values (e.g. entire column)
- OUTPUT: Single value
- Examples: `SUM()`, `MIN()`, `MAX()`, `AVG()`,etc.

#### SUM()

Add up all the values in a column

```sql
SUM(COLUMN_NAME)
```

**Example**:

```sql
select SUM(COST) from PETRESCUE
```

**Column Alias**:

```sql
select SUM(COST) as SUM_OF_COST from PETRESCUE
```



#### MIN, MAX

**MIN:** Return the MINIMUM value

**MAX:** Return the MAXIMUM value

- **Example**: Get the maximum **QUANTITY** of any ANIMAL:

  ```sql
  select MAX(QUANTITY) from PETRESCUE
  ```

- **Example**: Get the minimum value of ID column for Dogs:

  ```sql
  select MIN(ID) from PETRESCUE where ANIMAL='Dog'
  ```



#### Average

**AVG()** return the average value

- Example: Specify the Average value of COST:

  ```sql
  select AVG(COST) from PETRESCUE
  ```

#### SCALAR and STRING FUNCTIONS

**SCALAR:** Perform operations on every input value

**Examples:** `ROUND()`, `LENGTH()`, `UCASE`, `LCASE`

- Example: Retrieve the length of each value in ANIMAL:

  ```sql
  select LENGTH(ANIMAL) from PETRESCUE
  ```

#### UCASE, LCASE

Example: Retrieve ANIMAL values in UPPERCASE:

```sql
select UCASE(ANIMAL) from PETRESCUE
```

**Use the function in a WHERE clause:**

```sql
select * from PETRESCUE
where LCASE(ANIMAL) = 'cat'
```



## Date and Time Built-in Functions

### Date, Time Funcitons

Most databases contain special datatypes for dates and times.

DATE: `YYYYMMDD`

TIME: `HHMMSS`

TIMESTAMP: `YYYYSSDDHHMMSSZZZZZZ`

Date/Time functions:

```sql
YEAR(), MONTH(),DAY(), DAYOMONTH(), DAYOWEEK(),
DAYOYEAR(), WEEK(),HOUR(), MINUTE(), SECOND()
```

![image-20230706125434948](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230706_1688644476.png)

![image-20230706125515361](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230706_1688644516.png)

<img src="https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230706_1688644554.png" alt="image-20230706125553041" style="zoom:50%;" />



## Sub-Queries and Nested Selects

**Sub-query**: A query inside another query

```sql
select COLUMN1 from TABLE
where COLUMN2=(select MAX(COLUMN2) from TABLE)
```

- Cannot evaluate Aggregate functions like `AVG()` in the `WHERE` clause

- Therefore, use a sub-Select expression:

  ```sql
  select EMP_ID, F_NAME, L_NAME, SALARY
  from emplyees
  where SALARY<
  (select AVG(SALARY) from employee);
  ```

- Substitute column name with a sub-query

- Called Column Expressions

  ```sql
  select EMP_ID, SALARY, (select AVG(SALARY) from emplyees) AS AVG_SALARY
  from employee;
  ```

- Called **Derived Tables or Table Expressions**

  ```sql
  select * from (select EMP_ID, F_NAME, L_NAME, DEP_ID from employees) AS EMP4ALL;
  ```



## Working with Multiple Tables

**Ways to access multiple tables in the same query**:

1. Sub-queries
2. Implicit JOIN
3. JOIN operators (INNER JOIN, OUTER JOIN, etc.)

### Accessing Multiple Tables with Sub-queries

To retrieve **only** the **employee** records that correspond to departments in the **DEPARTMENTS** table:

```sql
select * from employees
where DEP_ID IN
(select DEPT_ID_DEP from departments)l
```

![image-20230706131341499](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230706_1688645623.png)

![image-20230706131416501](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230706_1688645658.png)



### Accessing multiple tables with Implicit Join

Specify 2 tables in the `FROM` clause:

```sql
select * from employees, departments;
```

**The result is a full join(or Cartesian join):**

- Every row in the first table is joined with every row in the second table
- The result set will have more rows than in both tables

**Use additional operands to limit the result set**:

```sql
select * from employees, departments
where employees.DEP_ID = departments.DEPT_ID_DEP;
```

**Use shorter aliases for table names:**

```sql
select * from employees E, departments D where E.DEP_ID = D.DEPT_ID_DEP
```

