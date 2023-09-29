---
tags: IBM
Week: 2
---

## IBM Cloud Gallery

Estimated Time (45 min)

**IBM Cloud Gallery**(云图库) is a growing collection of data sets, notebooks, and project templates. In this lab, you will use _IBM cloud Gallery_ to explore different datasets. As we have learnt in the course, the data is not only about numbers, it can be anything such as numeric data, text data, images, videos, audios etc. You will work on three samples.

**Sample 1** in which you will learn about the dataset in which <u>only numeric attributes are present</u>.

**Sample 2** in which you will learn about the dataset in which <u>numeric & text attributes are present</u>.

**Sample 3** in which you will analyze how the <u>Jupyter Notebooks</u> look like. How a <u>Data Scientist create the models</u>?

Let's take a look that how different datasets are used by Data Scientist.

#### Objectives :

You will learn to:

-   Explore the IBM Cloud Gallery
-   Evaluate Numeric dataset
-   Evaluate dataset with Non-Numeric attributes
-   Evaluate Jupyter Notebook

#### Exercise 1: Evaluate Numeric dataset

1.  Click on the link: [https://dataplatform.cloud.ibm.com/gallery](https://dataplatform.cloud.ibm.com/gallery?utm_medium=Exinfluencer&utm_source=Exinfluencer&utm_content=000026UJ&utm_term=10006555&utm_id=NA-SkillsNetwork-Channel-SkillsNetworkCoursesIBMDeveloperSkillsNetworkDS0101ENSkillsNetwork947-2022-01-01)
    
2.  Select _All Filters_. From **_Format_** select **_Data_** and from **_Topic_** select **_Energy & Utilities, Environment and Industry Accelerator_**
    

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0101EN-SkillsNetwork/labs/Module%202/images/filter_1.png)
![upgit_20221203_1670102065.png](https://raw.githubusercontent.com/RooNat/Myimages/main/2022/12/upgit_20221203_1670102065.png)

4.  Click on _UCI: Forest Fires_.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0101EN-SkillsNetwork/labs/Module%202/images/UCI_Forest.png)

5.  Preview the data using the **_Preview_** option.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0101EN-SkillsNetwork/labs/Module%202/images/data_UCI_Fires.png)

##### Explore the data

The data is related to **forest fires** where the aim is to predict ==the burned area of forest fires==, ==in the northeast region of Portugal==, by using meterological and other data.

**Attribute Information:**

1.  X - x-axis **spatial coordinate**(立体坐标) within the Montesinho park map: 1 to 9
2.  Y - y-axis spatial coordinate within the Montesinho park map: 2 to 9
3.  month - month of the year: 'jan' to 'dec'
4.  day - day of the week: 'mon' to 'sun'
5.  FFMC - FFMC index from the <u>FWI system</u>: 18.7 to 96.20
6.  DMC - DMC index from the FWI system: 1.1 to 291.3
7.  DC - DC index from the FWI system: 7.9 to 860.6
8.  ISI - ISI index from the FWI system: 0.0 to 56.10
9.  temp - temperature in Celsius degrees: 2.2 to 33.30
10.  RH - relative humidity in %: 15.0 to 100
11.  wind - wind speed in km/h: 0.40 to 9.40
12.  rain - outside rain in mm/m2 : 0.0 to 6.4
13.  area - the burned area of the forest (in ha): 0.00 to 1090.84

(this output variable is very **skewed**（曲解的） towards 0.0, thus it may make sense to model with the logarithm transform).
![upgit_20221203_1670102326.png](https://raw.githubusercontent.com/RooNat/Myimages/main/2022/12/upgit_20221203_1670102326.png)

### Exercise 2: Evaluate Non-Numeric dataset

The data doesn't have to be only based on numbers. Data can be text, images and other types as well. Let's look into data having text values.

1.  Use the _All Filters_. From _Format_ select **_Data_** and from **_Topic_** select _**Economy and Business**_.

You will get multiple datasets given. Scroll down and select _Airbnb Data for Analytics: Trentino Reviews_ (If you will not get the data use the **Load More** option)

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0101EN-SkillsNetwork/labs/Module%202/images/AIrbnb.png)

2.  Preview the data using the _Preview_ option.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0101EN-SkillsNetwork/labs/Module%202/images/Airbnb_preview.png)

##### Explore the data

**Airbnb**, Inc. is an <u>American company that operates an online marketplace for lodging, primarily homestays for vacation rentals, and tourism activities</u>. Airbnb guests may leave a review after their stay, and these can be used as an indicator of airbnb activity.The minimum stay, price and number of reviews have been used to estimate the occupancy rate, the number of nights per year and the income per month for each listing.

This data can be used in various ways - To (1) <u>analyze the star ratings of places</u>, to (2) <u>analyze the location preferences of the customers</u>, to (3) <u>analyze the tone and sentiment of customer reviews</u> and many more. Airbnb uses location data to improve guest satisfaction.

> 💡 Can you think of what you can use this data for?

The dataset comprises of three main tables:

-   **listings** - Detailed listings data showing **96 attributes** for each of the listings. Some of the attributes used in the analysis are **price(continuous)**, **longitude (continuous)**, **latitude (continuous)**, **listing\_type (categorical)**, is\_superhost (categorical), **neighbourhood (categorical)**, **ratings (continuous)** among others.
    
-   **reviews** - Detailed reviews given by the guests with 6 attributes. Key attributes include **date (datetime)**, **listing\_id (discrete)**, **reviewer\_id (discrete)** and **comment (textual)**.
    
-   **calendar** - Provides details about booking for the next year by listing. Four attributes in total including **listing\_id (discrete)**, **date(datetime)**, **available (categorical)** and **price (continuous)**.
    

### Exercise 3: Evaluate Jupyter Notebook

Use the _All Filters_. From **_Format_** select **_Notebook_** and select **_Finding optimal locations of new stores using Decision Optimization_** (If you will not find the notebook use the **Load More** option to load the notebooks)

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0101EN-SkillsNetwork/labs/Module%202/images/New_Store.png)

>[!question] What does **notebook** do?
>This notebook shows you how **Decision Optimization** can help to **prescribe decisions** for a complex constrained problem using Python to help determine the optimal location for a new store.

The objective is to **minimize the total distance** from **libraries to coffee** shops so that a book reader always gets to our coffee shop easily. It can be done by analyzing and displaying the location of the coffee shops on a map.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0101EN-SkillsNetwork/labs/Module%202/images/Notebook.png)

When we **validate the dataset**, the locations on map are separated.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0101EN-SkillsNetwork/labs/Module%202/images/loc_jupyter.png)

But it is impossible to determine where to ideally open the coffee shops by just looking at the map.

This is solved by ==**an optimization model**== that will help us determine where to locate the coffee shops in an optimal way.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMDeveloperSkillsNetwork-DS0101EN-SkillsNetwork/labs/Module%202/images/loc2_jupyter.png)

#### Summary

In this lab, you have learned about exploring datasets and notebooks in IBM cloud Gallery.
