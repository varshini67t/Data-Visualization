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

# RESULT
Thus,We have applied data visualization techniques for the given dataset.

