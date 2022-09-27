### Ex-04-Multivariate-Analysis
### AIM:
To perform Multivariate EDA on the given data set.

### Explanation:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

### ALGORITHM:
## STEP 1:
Import the built libraries required to perform EDA and outlier removal.

## STEP 2:
Read the given csv file

## STEP 3:
Convert the file into a dataframe and get information of the data.

## STEP 4:
Return the objects containing counts of unique values using (value_counts()).

## STEP 5:
Plot the counts in the form of Histogram or Bar Graph.

## STEP 6:
Use seaborn the bar graph comparison of data can be viewed.

## STEP 7:
Find the pairwise correlation of all columns in the dataframe.corr()

## STEP 8:
Save the final data set into the file

### PROGRAM:
Name : MIRUDHULA D


Register Number : 21222123060


import pandas as pd
import numpy as np
import seaborn as sbn
import matplotlib.pyplot as plt

df = pd.read_csv("SuperStore.csv")

df.head(10)

df.info()

df.describe()

df.isnull().sum()

df['Postal Code'] = df["Postal Code"].fillna(df['Postal Code'].mode()[0])
df.isnull().sum()

df.dtypes

sbn.scatterplot(df['Postal Code'],df['Sales'])

states=df.loc[:,["State","Sales"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Sales")

plt.figure(figsize=(17,7))

sbn.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("STATES")

plt.ylabel=("SALES")

plt.show()

states=df.loc[:,["State","Postal Code"]]

states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code")

plt.figure(figsize=(17,7))

sbn.barplot(x=states.index,y="Postal Code",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("STATES")

plt.ylabel=("Postal Code")

plt.show()

states=df.loc[:,["Segment","Sales"]]

states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales")

#plt.figure(figsize=(10,7))

sbn.barplot(x=states.index,y="Sales",data=states)

plt.xticks(rotation = 90)

plt.xlabel=("SEGMENT")

plt.ylabel=("SALES")

plt.show()

sbn.barplot(df['Postal Code'],df['Ship Mode'],hue=df['Region'])

df.corr()

sbn.heatmap(df.corr(),annot=True)

### OUTPUT
![o1](https://user-images.githubusercontent.com/94828147/192529249-931087d9-3a03-48f7-9225-2f049d12be13.png)


![o2](https://user-images.githubusercontent.com/94828147/192529530-1517942d-fe36-4f66-bedd-3ef103cc97c7.png)


![o3](https://user-images.githubusercontent.com/94828147/192529823-51487083-ffc8-4e78-b47f-383e7f549ebb.png)


![o4](https://user-images.githubusercontent.com/94828147/192529906-abbe2525-cccd-4c64-83fd-debec461e857.png)


![o5](https://user-images.githubusercontent.com/94828147/192530141-0bf87e75-eb8d-45c3-9f90-af3d05c9d431.png)


![o6](https://user-images.githubusercontent.com/94828147/192530170-d784eed4-78c4-4e31-9e3d-37c705c3d47b.png)

![o7](https://user-images.githubusercontent.com/94828147/192530195-868b0342-cfc7-4bef-9303-291d73ef80cd.png)


![o8](https://user-images.githubusercontent.com/94828147/192530209-09c9ecd1-1e7e-42bf-a662-27d19f5c0376.png)


![o9](https://user-images.githubusercontent.com/94828147/192530357-8e877f8b-f105-4cdf-8f52-cbb1c2a2c995.png)


![o10](https://user-images.githubusercontent.com/94828147/192530366-3a585b81-24b7-477c-b9a7-eda826c98569.png)



![o11](https://user-images.githubusercontent.com/94828147/192530451-c912288a-6265-481d-9902-356c39fb39cb.png)


![o13](https://user-images.githubusercontent.com/94828147/192530455-bbe9a39e-c113-48d0-9d55-1270d5bf9271.png)


### RESULT 


Thus the program to perform EDA on the given data set is successfully executed.









