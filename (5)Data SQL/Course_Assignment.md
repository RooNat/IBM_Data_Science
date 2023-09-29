---
module:5
tags: SQL
typora-copy-images-to: ./attachments
---

# Working with Real World Datasets

[toc]



## Working with CSV files

- Many real data sets are .CSV files

- .CSV: COMMA SEPARATED VALUES

- Example: DOGS.CSV

  ![image-20230724154358218](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690209839.png)

## Column names in First row

![image-20230724154559034](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690209960.png)

![image-20230724154703937](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690210025.png)

### Querying column names with spaces and special characters

By default, spaces are mapped to underscores:

![image-20230724154819150](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690210100.png)

![image-20230724155338513](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690210420.png)

## Splitting queries to multiple lines in Jupyter

Use backslash “\\" to split the query into multiple lines:

```sql
%sql select "Id", "Name_of_Dog", \
	from dogs \
	where "Name_of_Dog"='Huggy'
```

 Or use %%sql in the first row of the cell in the notebook:

```sql
%%sql
select "Id","Name_of_Dog",
	from dogs
	where "Name_of_Dog"='Huggy'
```



![image-20230724165424597](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690214066.png)



## Getting Table and Column Details

![image-20230724171413275](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690215255.png)

### Getting a list of tables in the database

![image-20230724171503701](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690215305.png)

![image-20230724171932725](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690215574.png)

![image-20230724172014407](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690215616.png)

To obtain the column names query syscat.columns:

```sql
select * from syscat.columns
where tabname = 'DOGS'
```

To obtain specific column properties:

```sql
select distinct(name), coltype, length
from sysibm.syscolumns
where tbname='DOGS'
```

![image-20230724172751258](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690216072.png)