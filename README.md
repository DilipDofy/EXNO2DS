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

## CODING AND OUTPUT:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
![Screenshot 2024-09-05 152455](https://github.com/user-attachments/assets/f0feb276-a94c-4ec6-af59-dbf7ea748463)

```
df.info()
```
![Screenshot 2024-09-05 152646](https://github.com/user-attachments/assets/ca315907-3a34-4722-a849-8aa9d6d2b52c)

```
df.shape
```
![Screenshot 2024-09-05 152723](https://github.com/user-attachments/assets/7cef25ae-1082-4522-9321-96e00c52203a)

```
df.set_index("PassengerId",inplace=True)
df.describe()
```
![Screenshot 2024-09-05 152852](https://github.com/user-attachments/assets/0f2a5ee5-a85d-4ecf-b952-c45b16fbcdd3)

```
df.shape
```
![Screenshot 2024-09-05 153003](https://github.com/user-attachments/assets/e02d755c-1cfe-4c2a-a1ed-c7684e6e7307)

```
df.nunique()
```
![Screenshot 2024-09-05 153102](https://github.com/user-attachments/assets/d9aa5f0e-52c3-43fc-8e32-d1a821694585)

```
df["Survived"].value_counts()
```
![Screenshot 2024-09-05 153145](https://github.com/user-attachments/assets/46e15a03-25c0-410d-a1cb-01fdc83358d1)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![Screenshot 2024-09-05 153229](https://github.com/user-attachments/assets/06505bab-6ac6-4231-8dda-841c106181be)

```
sns.countplot(data=df,x="Survived")
```
![Screenshot 2024-09-05 153327](https://github.com/user-attachments/assets/2574d7bf-c8c7-4626-b026-a03d2766aa07)

```
df
```
![Screenshot 2024-09-05 153422](https://github.com/user-attachments/assets/62ad8a53-cf0c-4510-aa9e-091e8f77296f)

```
df.Pclass.unique()
```
![Screenshot 2024-09-05 153507](https://github.com/user-attachments/assets/fb4fa5d5-3bac-4bce-b699-78fc3f4b9b9d)

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
![Screenshot 2024-09-05 153555](https://github.com/user-attachments/assets/1d76f527-0231-4034-9ead-943b2048beb9)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```
![Screenshot 2024-09-05 153651](https://github.com/user-attachments/assets/06a23145-3e5c-447d-beaf-0aa32157d6b4)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```
![Screenshot 2024-09-05 153738](https://github.com/user-attachments/assets/db07a589-c3f9-406f-9fd3-aa259a5b71d0)

```
df.boxplot(column="Age",by="Survived")
```
![Screenshot 2024-09-05 153826](https://github.com/user-attachments/assets/486f4099-0955-4915-a9ca-4f2c982e480a)

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
![Screenshot 2024-09-05 153917](https://github.com/user-attachments/assets/7f284ed6-82c1-49bc-aa64-fae768e40367)

```
sns.jointplot(x="Age",y="Fare",data=df)
```
![Screenshot 2024-09-05 154015](https://github.com/user-attachments/assets/78657f65-8ab9-4409-993f-34a431800e4a)

```
fig,ax1=plt.subplots(figsize=(8,5))
plt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)
```
![Screenshot 2024-09-05 154056](https://github.com/user-attachments/assets/42aed6f3-e17e-4517-b97e-f1a15aa7fcd0)

```
sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![Screenshot 2024-09-05 154153](https://github.com/user-attachments/assets/f3b97c4d-03ac-43e6-9dd3-3a781b0b2c3f)

```
corr=df.select_dtypes(include=['number']).corr()
sns.heatmap(corr,annot=True)
```
![Screenshot 2024-09-05 154243](https://github.com/user-attachments/assets/0c076cdc-5f99-4abb-92b0-ad06bd0b08cf)

```
sns.pairplot(df)
```
![Screenshot 2024-09-05 154431](https://github.com/user-attachments/assets/6e58083b-3dfc-43f7-80d8-387b9e9e42c3)
![Screenshot 2024-09-05 154450](https://github.com/user-attachments/assets/223f4792-749a-4596-82af-e88357e6ce5d)


# RESULT:
    Thus the data analysis has been implemented succesfully.
