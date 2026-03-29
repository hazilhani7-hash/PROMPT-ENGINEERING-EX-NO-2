# EX-02-Cross-Platform-Prompting-Evaluating-Diverse-Techniques-in-AI-Powered-Text-Summarization

## REG NO:212223020017
## NAME: Mohammed Hazil H

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
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/0e71ed5d-8a4c-4cee-ac4b-6a38a9ad8e78)

```
df.info()
```
![image](https://github.com/user-attachments/assets/7734fa49-775a-4810-b128-3a9f8ea6f804)
```
df.shape
```
![Screenshot 2025-03-26 143918](https://github.com/user-attachments/assets/e28f94c9-df0d-4a88-9e5b-2e5cebd9ea3c)
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/daf9f8f8-f74b-4fa1-80e6-d89b464b62aa)
```
df.shape
```
![image](https://github.com/user-attachments/assets/22471ff1-bba3-4d7b-a305-c95e129d4be0)
## Categorical Data Analysis
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/c13a0fe4-9e3b-4d6d-9df6-b4f670b24fc9)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/ae472d78-7625-4a07-9f48-08a789dde8b9)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/2775262a-c538-4730-8349-14a87c65f502)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/0ea664e2-cc6e-470a-9e5f-c73ea3d5f1d2)
```
df
```
![image](https://github.com/user-attachments/assets/a71ed9d8-2383-414f-bef4-36f4ea2d7429)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/c5cba959-0e65-4e8b-b8f2-84bf3dcbbc03)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/3bd373b8-543f-4660-89df-6777177bcb0d)
## Bivariate Analysis
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/284a9f01-d0a9-4df0-9e0e-bc75b538aa52)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/00e0e931-7481-4b60-a6d4-a0334be56615)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/9fa94b01-5862-4e65-9499-197743b6a266)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/7c8f74a5-27d4-40d6-919d-5b14d91b693f)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/b424409b-a840-41e5-9928-ad2b3e678e45)
## Multivariate Analysis
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/88b4d758-dade-41c2-b45a-31c4a3179b78)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/ea2bd36d-4acb-498a-b231-8049de35e46a)
## Co-relation
```
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/885d3e3d-006f-4ad3-a69e-dbbd8e55580f)
```
sns.pairplot(df)
```
![download](https://github.com/user-attachments/assets/a349a1e5-6f46-4e20-be47-10d9262447d9)










# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.

