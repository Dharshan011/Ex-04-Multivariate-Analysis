# Ex-04-Multivariate-Analysis
## AIM:
To perform Multivariate EDA on the given data set.

## EXPLANATION:
Exploratory data analysis is used to understand the messages within a dataset. This technique involves many iterative processes to ensure that the cleaned data is further sorted to better understand the useful meaning.The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.

## ALGORITHM:
## STEP 1
Import the built libraries required to perform EDA and outlier removal.

## STEP 2
Read the given csv file.

## STEP 3
Convert the file into a dataframe and get information of the data.

##STEP 4
Return the objects containing counts of unique values using (value_counts()).

##STEP 5
Plot the counts in the form of Histogram or Bar Graph.

## STEP 6
Use seaborn the bar graph comparison of data can be viewed.

## STEP 7
Find the pairwise correlation of all columns in the dataframe.corr() .

## STEP 8
Save the final data set into the file.

### PROGRAM:
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

data.isnull().sum()

data.dtypes

sns.scatterplot(data['Postal Code'],data['Sales'])

states=data.loc[:,["State","Sales"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("STATES")
plt.ylabel=("SALES") 
plt.show()

states=data.loc[:,["State","Postal Code"]] 
states=states.groupby(by=["State"]).sum().sort_values(by="Postal Code") 
plt.figure(figsize=(17,7)) 
sns.barplot(x=states.index,y="Postal Code",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("STATES") 
plt.ylabel=("Postal Code") 
plt.show()

states=data.loc[:,["Segment","Sales"]] 
states=states.groupby(by=["Segment"]).sum().sort_values(by="Sales") 
plt.figure(figsize=(10,7)) 
sns.barplot(x=states.index,y="Sales",data=states) 
plt.xticks(rotation = 90) 
plt.xlabel=("SEGMENT") 
plt.ylabel=("SALES") 
plt.show()

sns.barplot(data['Postal Code'],data['Ship Mode'],hue=data['Region'])

data.corr()

sns.heatmap(data.corr(),annot=True)
```
## OUTPUT:
## HEAD()
![Screenshot 2023-04-17 110917](https://user-images.githubusercontent.com/113497491/232392895-d63da13a-1977-4a0a-840a-bb00db76cfbb.png)

## INFO()
![Screenshot 2023-04-17 110927](https://user-images.githubusercontent.com/113497491/232392927-8391bead-ae3d-4708-b0cf-938ddebb24b7.png)


## DESCRIBE()
![Screenshot 2023-04-17 110935](https://user-images.githubusercontent.com/113497491/232392957-c66fe20c-cf57-4fbe-a555-cf0dd6357a52.png)


## DATATYPE()
![Screenshot 2023-04-17 110942](https://user-images.githubusercontent.com/113497491/232392979-afd54391-75a1-4cef-a9c7-708942da231a.png)


## ISNULL()
![Screenshot 2023-04-17 110949](https://user-images.githubusercontent.com/113497491/232393028-4ab270b1-a038-4f8f-a90f-a16e8aae4b02.png)


## SCATTER PLOT
![Screenshot 2023-04-17 110959](https://user-images.githubusercontent.com/113497491/232393049-78d2b1ee-b6d7-4ec9-8eaf-a7e8283452bd.png)


## BARPLOT
![Screenshot 2023-04-17 111009](https://user-images.githubusercontent.com/113497491/232393090-c9b83e1e-d755-44da-aa79-298be0f6172b.png)
![Screenshot 2023-04-17 111020](https://user-images.githubusercontent.com/113497491/232393108-086f5ccb-30a1-4a10-b604-62ed223af6d2.png)

## SEGMENTATION

![Screenshot 2023-04-17 111033](https://user-images.githubusercontent.com/113497491/232393124-baa3afee-c235-49c8-b455-7c955c477970.png)

## SUBPLOTS
![Screenshot 2023-04-17 111043](https://user-images.githubusercontent.com/113497491/232393148-4313b2d5-1224-4950-a216-f49b267955de.png)


## CORRESSION
![Screenshot 2023-04-17 111051](https://user-images.githubusercontent.com/113497491/232393187-692d5eb6-0cf7-4488-a486-f82a39c15d68.png)


## HEATMAP()
![Screenshot 2023-04-17 111059](https://user-images.githubusercontent.com/113497491/232393229-2604341e-41f0-411d-a696-bd9dc0b22dab.png)


## RESULT
Hence The Performance of the Multivariate EDA on the given data set is verified.
