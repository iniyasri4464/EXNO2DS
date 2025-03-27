# EXNO2DS
## NAME: INIYASRI S
## REGNO: 212223230081
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/c21fab0e-a896-4ea2-8a5e-6fbae5d2aa6b)
```
df.info()
```
![image](https://github.com/user-attachments/assets/dfca85ab-205f-42df-b313-34cef856f7b3)
```
df.set_index("PassengerId",inplace =True)
df.shape
```
![image](https://github.com/user-attachments/assets/5b1f4b1b-5c04-4fdd-a79d-b1aef5966726)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/3c233df9-f771-46b3-9550-c5b28d949f60)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/cd6bf5ab-f600-4520-ac90-1e41d022f93a)
```
per=(df['Survived'].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/8bef3d5d-2fe0-49da-bfe9-b439b00936e5)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/ad1d6bbe-7139-4f2f-b8ca-ad6e0dad2ec7)
```
fig, ax1 = plt.subplots(figsize=(5,5))
graph=sns.countplot(ax=ax1,x= 'Survived', data=df)
graph.set_xticklabels (graph.get_xticklabels (), rotation=90)
for p in graph.patches:
  height = p.get_height()
  graph.text(p.get_x()+p.get_width()/2., height + 0.1, height,ha="center")
```
![image](https://github.com/user-attachments/assets/4f599a25-d40f-41de-a49b-2ffa6a886058)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/ecf59b5d-57be-4fdd-bb3c-0e2250be04bb)
```
df.rename(columns = {'Sex':"Gender"},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/496403c4-d662-43e9-b06b-6768fbb5f2180)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/8b0820f6-6d58-4c59-85b8-bf963ed3f666)
```
fig, ax1 = plt.subplots(figsize=(8,5))
graph=sns.countplot(ax=ax1,data=df,x="Survived", hue="Pclass", palette="rainbow")
graph.set_xticklabels (graph.get_xticklabels())
for p in graph.patches:
  height = p.get_height()
  graph.text(p.get_x()+p.get_width()/2, height+ 20.8, height,ha="left")
```
![image](https://github.com/user-attachments/assets/fabd1a92-52b4-476a-a919-65f9995eb66e)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/cab7c140-1def-4f67-88e7-843044cd7ebe)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/c99bc8f0-3074-4883-9703-b20d94dcd5df)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/c38a18de-c8bb-407c-8e36-d1fbcd2fea9e)
```
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue="Gender",data=df)
```

![image](https://github.com/user-attachments/assets/30d2c7e0-9efd-445d-a70c-3b66afe058f8)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![image](https://github.com/user-attachments/assets/d01f7e3d-0cb8-459a-aaec-f0d2962330fc)
```
g= sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass", kind = "count", legend=True)
g.fig.set_size_inches(8,5)
g.fig.subplots_adjust(top=0.81,right=0.86)
ax =g.facet_axis(0,0)
for p in ax.patches:
   ax.text(p.get_x()-0.01,p.get_height()*1.02,'{0:.1f}'.format(p.get_height()),color='red',rotation='horizontal',size='small')
```
![image](https://github.com/user-attachments/assets/23ebbf75-ef45-4ca0-90ce-71aa531af1bd)
```
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/eab90686-ddf4-4df0-bc40-4641b9f83aad)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/1733817f-b4f7-449f-ab92-fabe00105385)


# RESULT
```
      Thus, the outputs verifies that the data set has been applied the EDA process and methods.
```
