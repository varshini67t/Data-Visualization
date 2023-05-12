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

sns.barplot(x=data['Segment'],y=data['Profit'])

ii)City

sns.barplot(x=data['City'],y=data['Profit'])

iii)States

sns.barplot(x=data['Region'],y=data['Profit'])

iv)Segment And Ship Mode

sns.barplot(x=data['Ship Mode'],y=data['Profit'])

v)Segment, Ship mode and Region

sns.barplot(x=data['Region'],y=data['Profit'])

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
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/29c8d9e6-d141-4565-a1d2-1960e3e29be6)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/e86721d4-1830-47be-a6d5-05d3335eb470)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/fe806d75-ee8a-4ca6-a48a-a2a9f268f702)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/aa54d71a-0196-4c72-9e1a-a12bf7a8ef9f)
![image](https://github.com/varshini67t/Data-Visualization/assets/107982953/0fa097e5-933b-4b0a-a37a-f59c41b313fa)

# RESULT
Thus,We have applied data visualization techniques for the given dataset.

