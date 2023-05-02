# Data-Visualization
# AIM
To Perform Data Visualization on a complex dataset and save the data to a file.

# ALGORITHM

STEP 1-Read the given Data

STEP 2-Clean the Data Set using Data Cleaning Process

STEP 3-Apply Feature generation and selection techniques to all the features of the data set

STEP 4-Apply data visualization techniques to identify the patterns of the data.

# CODE

import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from scipy import stats
import seaborn as sns
data = pd.read_csv('/content/Superstore.csv',encoding='windows-1252')
data.head()


data.info()

data.isnull().sum()

1.Which Segment has Highest sales?

sns.countplot(x=data['Segment'],data=data)
plt.title("No.of.sales in segment")

2.Which City has Highest profit?

sns.barplot(x=data['City'],y=data['Profit'])
plt.title("NO.of.Profit in cities")

3.Which ship mode is profitable?

sns.countplot(x=data['Ship Mode'],data=data)
plt.title("NO.OF.Profits in ship mode")

4.Sales of the product based on region.

sns.boxplot(x=data['Region'],y=data['Sales'])
plt.title("Sales of product based on region")

5.Find the relation between sales and profit.

sns.scatterplot(x=data['Sales'],y=data['Profit'])

6.Find the relation between sales and profit based on the following category.

i) Segment

sns.scatterplot(x=data['Sales'],y=data['Profit'],hue=data['Segment'])

ii)City

sns.scatterplot(x=data['Sales'],y=data['Profit'],hue=data['City'])

iii)States

sns.scatterplot(x=data['Sales'],y=data['Profit'],hue=data['Region'])

iv)Segment And Ship Mode

sns.scatterplot(x=data['Sales'],y=data['Ship Mode'],hue=data['Segment'])

v)Segment, Ship mode and Region

sns.scatterplot(x=data['Segment'],y=data['Ship Mode'],hue=data['Region'])

# OUTPUT
![image](https://user-images.githubusercontent.com/107982953/235736961-a4a066c6-f731-4337-b5cc-ea0821137f2d.png)
![image](https://user-images.githubusercontent.com/107982953/235737066-7d0f5042-9097-46e7-a7ba-a6418830f26d.png)
![image](https://user-images.githubusercontent.com/107982953/235737145-5f9f5c9c-f181-4ab0-83f2-f4b35dcb8c0a.png)
![image](https://user-images.githubusercontent.com/107982953/235737209-13d43c3b-eccd-4d59-a195-7722e9e0012b.png)
![image](https://user-images.githubusercontent.com/107982953/235737275-44d76011-478c-487a-955b-c0f9df6cf094.png)
![image](https://user-images.githubusercontent.com/107982953/235737355-8cb6e55a-5e93-47f4-a76d-18ca4d54da64.png)
![image](https://user-images.githubusercontent.com/107982953/235737523-8f1271ee-005a-482f-b428-c6b00c271e00.png)
![image](https://user-images.githubusercontent.com/107982953/235737603-3e130fbf-a781-4de3-9118-ba70750ae1d5.png)
![image](https://user-images.githubusercontent.com/107982953/235737678-96af1d18-47dd-4357-8e86-dbbfb50bbe1a.png)
![image](https://user-images.githubusercontent.com/107982953/235737767-73fc7acf-b588-41bf-adc3-75cd269cec46.png)

# RESULT
Thus,We have applied data visualization techniques for the given dataset.

