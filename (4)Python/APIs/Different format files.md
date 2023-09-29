---
module:5
typora-copy-images-to: ./attachments
---

# Different File Formats(css, xml, json, xlsx)

[toc]

**This chapter's objectives are:**

- Define different file formats such as csv, xml, and json.
- Write simple programs to read and output data
- List what Python libraries are needed to extract data



## Reading CSV Files

The first python library to become familiar with is called **pandas** , by importing this library in the beginning of the code we are then able to easily **read the different file types**. 

```python
import pandas as pd
file="FileExample.csv"
df=pd.read_csv(file)
```

With this example, there were no **headers** for the data so it added the **first line as the header.** Since we do not want the first line of data as the header, we easily solve this by adding a data frame attribute 

```python
df.columns=['Name', 'Phone Number', 'Birthday']
```

We use the variable `df` to call the file and then add the columns attribute by adding this one line to our program. We can then neatly organize the data output into the specified headers for each column.



## Reading JSON Files

```python
import json
with open('filesample.json','r') as openfile:
  json_object=json.load(openfile)
  print(json_object)
```





## Reading XML Files

- The first step to read this type of file is to import `xml` by importing this library 
- We can then use the `etree` attribute to parse the `xml` file 
- We then **add the column headers**
- Assign them to the data frame then create a loop to go through the document to collect the necessary data and append the data to a data frame.

```python
import pandas as pd
import xml.etree.ElementTree as etree
tree=etree.parse("fileExample.xml")
root=tree.getroot()
columns=["Name","Phone Number", "Birthday"]
df=pd.DataFrame(columns=columns)
```

![image-20230630121724290](https://raw.githubusercontent.com/RooNat/Myimages/main/2023/06/upgit_20230630_1688123847.png)