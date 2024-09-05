# EXNO2DS
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
```
```
import seaborn as sns
df=pd.read_csv("titanic_dataset.csv")
df
```
![image](https://github.com/user-attachments/assets/9eee8173-554d-44db-af89-bd2bd4d73be2)
```
df.info()
```
![image](https://github.com/user-attachments/assets/eb71a913-682e-478b-bd55-b02cf27d0d6c)
```
df.shape
```
![image](https://github.com/user-attachments/assets/97425180-81f8-48e1-b881-f4ef3d6ae249)
```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![image](https://github.com/user-attachments/assets/43e761fa-54a6-4027-8ee9-b9af07993862)
```
df.shape
```
![image](https://github.com/user-attachments/assets/5490999c-9591-4e07-a65c-8208cc902983)

# Categorical data analysis

```

df.nunique()
```
![image](https://github.com/user-attachments/assets/d2384fa1-4396-45c6-b69e-d8eed2df88e3)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/8c3d4792-d30d-4eb1-97f1-2a37b8bc7114)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/ccf52af6-e5d4-4b64-b566-0bc187940b0b)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/1214378c-6619-4e23-8e54-7066be6d2690)
```
df
```
![image](https://github.com/user-attachments/assets/5dcb1d2b-c890-4424-b6ea-4d01c7b564ca)
```
df.Pclass.unique()
```
![image](https://github.com/user-attachments/assets/0f9b8873-33cb-4856-a5ca-3284a8fb99fe)
```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/ecafa9c5-599a-48ac-93c3-e3039242e47b)
# Bivariate Analysis
```

sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![image](https://github.com/user-attachments/assets/d1e2a1f7-c475-4fc8-8344-a779fe29284c)
```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![image](https://github.com/user-attachments/assets/fcadfe0b-2752-44da-aa29-7688f157cacf)
```
df.boxplot(column="Age",by="Survived")
```
![image](https://github.com/user-attachments/assets/549a91f7-8fe7-415c-b9a8-ad793e6be9f0)
```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/f0dd96d5-13f9-462d-9930-8ff734812b9e)
```
sns.jointplot(x="Age",y="Fare",data=df)
```
![image](https://github.com/user-attachments/assets/173a85e1-4660-4974-8e71-6c2880c4771d)

# Multivariate Analysis
```

fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![image](https://github.com/user-attachments/assets/820956c3-d461-4993-92f2-c5edf8c30963)
```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![image](https://github.com/user-attachments/assets/44c6a3c5-a313-471a-88ad-04396ee1b40e)

# Co-relation
```

corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/1572971f-0d12-40ec-ad93-4b7e2050382c)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/cf7f48a3-07a6-473d-bba5-9e0129a4c939)
















# RESULT
We have performed Exploratory Data Analysis on the given data set successfully.
