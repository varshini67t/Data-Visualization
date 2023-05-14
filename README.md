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

sns.barplot(x=data['Segment'],y=data['Sales'])
plt.title("Segment VS Sales")

2.Which City has Highest profit?

sns.barplot(x=data['City'],y=data['Profit'])
plt.title("NO.of.Profit in cities")

City=data.loc[:,["City","Profit"]]
data.head(5)
City=City.groupby(by=["City"]).sum().sort_values(by="Profit")
plt.figure(figsize=(17,7))
sns.barplot(x=City.index,y="Profit",data=City)
plt.xticks(rotation = 90)
plt.xlabel=("City")
plt.ylabel=("Profit")
plt.show()

data.sort_values(by=['City'],inplace=True)
3.Which ship mode is profitable?

sns.barplot(x=data['Ship Mode'],y=data['Profit'])
plt.title("NO.OF.Profits in ship mode")

4.Sales of the product based on region.

sns.barplot(x=data['Region'],y=data['Sales'])
plt.title("Sales of product based on region")

5.Find the relation between sales and profit.

sns.lineplot(x=data['Sales'],y=data['Profit'])

6.Find the relation between sales and profit based on the following category.

i) Segment

grouped_data = data.groupby('Segment')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
ax.legend()
plt.title("Sales and Profit based on Segment")
plt.show()

ii)City

grouped_data = data.groupby('City')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('City')
ax.set_ylabel('Value')
ax.legend()
plt.title("Sales and Profit based on City")
plt.show()

iii)States

grouped_data = data.groupby('State')[['Sales', 'Profit']].mean()
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
ax.bar(grouped_data.index, grouped_data['Sales'], label='Sales')
ax.bar(grouped_data.index, grouped_data['Profit'], bottom=grouped_data['Sales'], label='Profit')
ax.set_xlabel('State')
ax.set_ylabel('Value')
ax.legend()
plt.title("Sales and Profit based on States")

iv)Segment And Ship Mode

grouped_data = data.groupby(['Segment', 'Ship Mode'])[['Sales', 'Profit']].mean()
pivot_data = grouped_data.reset_index().pivot(index='Segment', columns='Ship Mode', values=['Sales', 'Profit'])
# Create a bar chart of the grouped data
fig, ax = plt.subplots()
pivot_data.plot(kind='bar', ax=ax)
ax.set_xlabel('Segment')
ax.set_ylabel('Value')
plt.legend(title='Ship Mode')
plt.legend(loc="best")
plt.title("Sales and Profit based on Segment and Ship mode")
plt.show()

v)Segment, Ship mode and Region

grouped_data = data.groupby(['Segment', 'Ship Mode','Region'])[['Sales', 'Profit']].mean()
pivot_data = grouped_data.reset_index().pivot(index=['Segment', 'Ship Mode'], columns='Region', values=['Sales', 'Profit'])
sns.set_style("whitegrid")
sns.set_palette("Set1")
pivot_data.plot(kind='bar', stacked=True, figsize=(8, 5))
plt.legend(title='Region')
plt.legend(loc='best')
plt.title("Sales and Profit based on Segment,Ship mode and Region")

# OUTPUT
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/96b091b0-45a9-46bc-b464-9340aacd2b55)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/15360cfd-a2a6-4a09-85b4-adf9a68eb39c)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/834fbbd0-27c0-41c2-b6c9-173377a8dadd)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/e18880fc-7daa-46c8-940f-7702dd809b38)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/e0483cd7-eac0-40db-af4e-2c2d85c055bf)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/4dfa4ded-509c-4584-800b-00946e6290f7)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/25392640-f20c-4dc0-9043-aa9048cb57f4)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/f3f13433-8fdc-46a5-909f-2fc3b32345a4)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/4e77647d-eaa7-4991-8c3b-a0f2a7ff4eda)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/a1d78a44-8f61-40db-a1fa-76de87a1fede)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/95466807-460c-4843-ae09-79399bacee45)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/9beb503c-c642-4f53-a34c-c1b4f788718b)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/b9c93e75-5e49-4c99-ba02-5148ddb0d6eb)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/0898a0b9-2e44-42a6-93e8-53370dd8a1d5)

# RESULT
Thus,We have applied data visualization techniques for the given dataset.

