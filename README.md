# Ex-04-Multivariate-Analysis
# AIM:
To perform Multivariate EDA on the given data set.

# EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

# ALGORITHM:
# STEP 1:
Import the built libraries required to perform EDA and outlier removal.
# STEP 2:
Read the given csv file.
# STEP 3:
Convert the file into a dataframe and get information of the data.
# STEP 4:
Return the objects containing counts of unique values using (value_counts()).
# STEP 5:
Plot the counts in the form of Histogram or Bar Graph.
# STEP 6:
Use seaborn the bar graph comparison of data can be viewed.
# STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr() .
# STEP 8:
Save the final data set into the file.

# PROGRAM:

NAME:VAISHNAVI S
REG NO:212222230165.
```
import pandas as pd
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
data=pd.read_csv("SuperStore.csv")
data

data.head()

data.info()

data.describe()

data.dtypes

data.isnull().sum()

data['Postal Code']=data['Postal Code'].fillna(data['Postal Code'].mode()[0])
data.isnull().sum()

sns.scatterplot(x=data['Country'],y=data['Sales'],data=data)

states=data.loc[:,["Region","Sales"]] 
states=states.groupby(by=["Region"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("REGION")
plt.ylabel=("SALES") 
plt.show()

states=data.loc[:,["State","Sales"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("SALES") 
plt.ylabel=("STATES") 
plt.show()

states=data.loc[:,["Category","Sales"]] 
states=states.groupby(by=["Category"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(10,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("CATEGORY") 
plt.ylabel=("SALES") 
plt.show()

sns.barplot(data['Postal Code'],data['Ship Mode'],hue=data['Region'])

data.corr()

sns.heatmap(data.corr(),annot=True)
```
# OUTPUT:
# DATASET
![Screenshot 2023-04-09 185937](https://user-images.githubusercontent.com/118541897/230775619-25255fff-a58f-4912-932e-a7357ae6c8ed.png)

# HEAD()
![Screenshot 2023-04-09 190251](https://user-images.githubusercontent.com/118541897/230775883-b6034f09-4a32-4bf9-8e02-5b52d05f50be.png)

 
# INFO()
![Screenshot 2023-04-09 190719](https://user-images.githubusercontent.com/118541897/230775990-0b2e8af3-303a-40ea-b923-a4d1e5e7267b.png)


# DESCRIBE()
![Screenshot 2023-04-09 190726](https://user-images.githubusercontent.com/118541897/230775994-65eba8aa-d7b5-4a3c-a914-9d47788592d6.png)


# DATATYPE()
![Screenshot 2023-04-09 190734](https://user-images.githubusercontent.com/118541897/230775998-d0e90506-915c-4bf7-8bb5-a630f6c204f5.png)


# ISNULL()
![Screenshot 2023-04-09 190741](https://user-images.githubusercontent.com/118541897/230776003-41313e26-fd17-4cbf-a6c6-5427882802a6.png)


# Postal code has outliers.
![Screenshot 2023-04-09 190748](https://user-images.githubusercontent.com/118541897/230776023-58fed891-d6d5-4316-8987-17dec7b2b27c.png)

# After removing outliers from Postal Code.

# MULTIVARIATE ANALYSIS
# SCATTER PLOT
![Screenshot 2023-04-09 190758](https://user-images.githubusercontent.com/118541897/230776044-6bf65f09-ded3-47a2-9b81-7760979fab3c.png)

# BARPLOT
![Screenshot 2023-04-09 191236](https://user-images.githubusercontent.com/118541897/230776196-19ac7799-4988-4e15-b708-cfd402908b5c.png)

![Screenshot 2023-04-09 191154](https://user-images.githubusercontent.com/118541897/230776218-d3ef37e2-fb06-4948-84bf-1796f63f3e94.png)

# SEGMENTATION
![Screenshot 2023-04-09 191459](https://user-images.githubusercontent.com/118541897/230776440-094d2edd-cbc1-4919-b3f1-5bf25a0a14e3.png)

# CORRESSION
![Screenshot 2023-04-09 191604](https://user-images.githubusercontent.com/118541897/230776412-5c913d6e-7aa2-4549-9c42-328562d3a651.png)

# HEATMAP()
![Screenshot 2023-04-09 191611](https://user-images.githubusercontent.com/118541897/230776403-2ffc96a4-1d33-44b8-8afc-582aadd5b70e.png)

# RESULT
Hence The Performance of the Multivariate EDA on the given data set is verified.
