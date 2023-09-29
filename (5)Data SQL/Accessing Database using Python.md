---
module:4
tags: SQL
typora-copy-images-to: ./attachments
---

# Accessing Databases using Python

[toc]

## How to Access Databases using Python

![image-20230724134759739](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690202881.png)

![image-20230724134834617](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690202915.png)

### APIs used by popular SQL-based DBMS systems

![image-20230724135002225](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690203004.png)

## Writing Code Using DB-API

![image-20230724135126979](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690203091.png)

### Concepts of the Python DB API

![image-20230724135529219](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/09/upgit_20230914_1694686948.png)



#### What are connection methods?

- .cursor()
- .commit()
- .rollback()
- .close()

#### What are cursor methods?

![image-20230724135720181](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690203442.png)

### What is a database cursor?

A database cursor is a control structure that enables traversal over the records in a database. It behaves like a file name or file handle in a programming language.  Just as a program opens a file to access its contents,  it opens a cursor to gain access to the query results. Similarly, the program closes a file to end its access and closes a cursor to end access to the query results.

![image-20230724140048698](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690203650.png)

## Connecting to a database using ibm_db API

### What is ibm_db?

![image-20230724140236185](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690203758.png)

### Identify database connection credentials

![image-20230724140327560](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690203809.png)

### Create a database connection

![image-20230724140355103](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690203839.png)

### Close the database connection

Close connections so that we can avoid unused connections taking up resources. 

```python
ibm_db.close(conn)
```

## Creating tables, Loading data and querying data

![image-20230724140846316](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690204127.png)

![image-20230724140855799](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690204137.png)

![image-20230724140932592](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690204174.png)

![image-20230724140954017](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690204195.png)

![image-20230724141008541](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690204209.png)

![image-20230724141026667](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690204228.png)

![image-20230724141035656](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690204237.png)

![image-20230724141111320](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690204272.png)

## Introducing SQL Magic

### Objective

In this reading, you will learn about the SQL magic commands.

Jupyter notebooks have a concept of **Magic** commands that can simplify working with Python, and are particularly useful for data analysis. Your notebooks can have two types of magic commands:

- **Cell magics:** start with a double **%%** sign and apply to the entire cell
- **Line magics:** start with a single **%** (percent) sign and apply to a particular line in a cell

Their usage is of the format:

**%magicname arguments**

So far in the course you learned to accessed data from a database using the Python DB-API (and specifically ibm_db). With this API execution of queries and fetching their results involves multiple steps. You can use the **SQL Magic** commands to execute queries more easily.

For example if you want to execute the a query to select some data from a table and fetch its results, you can simply enter a command like the following in your Jupyter notebook cell:

**%sql select \* from tablename**

Although SQL magic simplifies working with databases, it has some limitations. For example, unlike DB-API, there are no explicit methods to close a connection and free up resources.

In the following tutorial you will learn how to work with SQL magic.



## Analysing data with python

**Example**: McDonald's menu nutrition facts

The data set used in this lesson has been obtained from the nutritional facts for McDonald's menu from Kaggle. We need to create a table on Db2 to store the McDonald's menu nutrition facts data set that we will be using. 

We will also be using the console provided by Db2 for this process. There are four steps involved in loading data into a table, 

- Source
- Target
- Define
- Finailze

We first load the spreadsheet into the Db2 using the console. We then select the target schema, and then you will be given an option to load the data into an existing table or create a new table.

Db2 Warehouse allows you to analyze data using in-database analytics, APIs, RStudio or Python. The data has been loaded into our relational database. You can run Python scripts that retrieve data from and write data to a Db2 database.

![image-20230724142022264](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690204823.png)

![image-20230724142146921](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690204909.png)

![image-20230724142218232](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690204945.png)

### Learn about your data

![image-20230724142301929](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690204983.png)

![image-20230724142423481](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690205064.png)

Which food item has the maximum sodium content? We first use visualization to explore the sodium content of food items. Using the swarm plot method provided by the Seaborne package, we create a categorical scatter plot as shown on the right, then give as the input, category on the x-axis, sodium on the y-axis, and the data will be the data frame DF that contains the nutritional data set from McDonald's. The plot shows the sodium values for the different food items by category. Notice a high value of around 3,600 for sodium on the scatter plot. 

![image-20230724142541216](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690205142.png)

To check the values of sodium levels in the food items within the dataset, we use the code as shown in code 1. The describe method is used to understand the summary statistics associated with sodium. Notice that the maximum value of sodium is given as 3,600. Now let's further explore the row associated with the maximum sodium variable as shown in code 2. We use the idxmax method to compute the index values, at which the maximum value of sodium is obtained in the data frame. We see that the output is 82.

Now lets find the item name associated with the 82nd item in our data frame. As shown in code 3, we will use the .at method to find the item name by passing the index of 82 and the column name item, to be returned for the 82nd row. Finally, we find that the food item on the menu that has a highest sodium content is Chicken McNuggets, 40 pieces. 

![image-20230724142750674](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690205274.png)

Visualizations are very useful for initial data exploration. They can help us understand relationships, patterns, and outliers in the data. Let's first create a scatter plot with protein on the x-axis, and total fat on the y-axis. Scatter plots are very popular visualization tools and show the relationship between two variables with a point for each observation. To do this, we can use the joint plot function provided by the Seaborn package, and give as input, protein on the x-axis and total fat on the y-axis. And the data will be the data frame DF that contains the nutritional data set from McDonald's. The output scatter plot is shown on the right side. The plot has an interesting shape. It shows the correlation between the two variables: protein and fat. 

![image-20230724142954719](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690205396.png)

![image-20230724143051183](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690205452.png)

Correlation is a measure of association between two variables, and has a value of between -1 and +1. We see that the points on the scatter plot are closer to a straight line in the positive direction. So we have a positive correlation between the two variables. On the top right corner of the scatter plot, we have the values of the Pearson correlation- 0.81 and the significance of the correlation denoted as P - which is a good value that shows the variables are certainly correlated. The plot also shows two histograms: one on the top and the other on the right side. The histogram on the top is that of the variable protein, and the histogram on the right side is that of the variable total fat. 

The histogram on the top is that of the variable protein, and the histogram on the right side is that of the variable total fat. We also noticed that there is a point on the scatter plot outside the general pattern. This is a possible outlier. Now let's see how we can visualize data using box plots. Box plots are charts that indicate the distribution of one or more variables. The box in a box plot captures the middle 50 percent of data.

![image-20230724143219615](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/07/upgit_20230724_1690205541.png)

Lines and points indicate possible skewness and outliers. Let's create a box plot for sugar. The function we are going to use is box plot from the Seaborn package. We give the column name sugars as input to the box plot function. The output is shown on the right side, where we had the box plot with average values of sugar and food items around 30 grams. We also notice a few outliers that indicate food items with extreme values of sugar. There exist food items in the data set that have sugar content of around 128 grams. Candies maybe among these high sugar content food items on the menu. 

