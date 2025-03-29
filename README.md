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

Developed by: BALA B
Register NO : 212224100005

```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
bala=pd.read_csv("/content/titanic_dataset.csv")
bala
```
![Screenshot 2025-03-27 112801](https://github.com/user-attachments/assets/13afc144-c707-475d-9b92-a9ec0c1beae9)
```
bala.info()
```
![Screenshot 2025-03-27 112822](https://github.com/user-attachments/assets/f244d7f3-ef97-4d69-b4f9-05acb2301b1a)
```
bala.shape
```
![Screenshot 2025-03-29 103638](https://github.com/user-attachments/assets/de0fd42d-5799-457c-8a2d-ee5f249eb973)


```
bala.set_index("PassengerId",inplace=True)
bala.describe()
```
![Screenshot 2025-03-27 112838](https://github.com/user-attachments/assets/a76c4f8d-f935-45bb-bf5a-1568d280fbf0)
```
bala.shape
```
![Screenshot 2025-03-29 103644](https://github.com/user-attachments/assets/cba7095d-5440-4ba0-b511-f0dc53772a00)
## Categorical data analysis

```
bala.nunique()
```
![Screenshot 2025-03-27 112851](https://github.com/user-attachments/assets/9336c1e2-0868-4dda-89b9-6cc451d73b05)


```
bala["Survived"].value_counts()
```
![Screenshot 2025-03-27 112904](https://github.com/user-attachments/assets/a3b7e4ac-5029-4822-9fbf-b0429914c9f0)
```
per=(bala["Survived"].value_counts()/bala.shape[0]*100).round(2)
per
```
![Screenshot 2025-03-27 112926](https://github.com/user-attachments/assets/9681d667-b0ed-4dbb-b7e6-b3ab804ebd72)
```
sns.countplot(data=bala,x="Survived")
```
![Screenshot 2025-03-27 112944](https://github.com/user-attachments/assets/3a6dfb0e-c0ed-48ef-b04d-8c4f18b76308)
```
bala
```
![Screenshot 2025-03-29 104106](https://github.com/user-attachments/assets/7277aef7-f451-4410-a56a-89e1b0a953e9)

```
bala.Pclass.unique()
```
![Screenshot 2025-03-27 112952](https://github.com/user-attachments/assets/f970de42-90d4-4502-b05f-28d2393f8747)

```
bala.rename(columns={'Sex':'Gender'},inplace=True)
bala
```
![Screenshot 2025-03-27 113010](https://github.com/user-attachments/assets/51d8a83f-d388-4f5a-9aa9-63a38c359de3)
## Bivariate Analysis 
```
sns.catplot(x="Gender",col="Survived",kind="count",data=bala,height=5,aspect=.7)
```
![Screenshot 2025-03-27 113028](https://github.com/user-attachments/assets/9df74e8d-9a8b-4823-bbc7-bb5d580a8d52)
```
sns.catplot(x="Survived",hue="Gender",data=bala,kind="count")
```
![Screenshot 2025-03-27 113044](https://github.com/user-attachments/assets/04d31ac1-2066-4033-aee7-eb7461271248)

```
bala.boxplot(column="Age",by="Survived")
```
![Screenshot 2025-03-27 113056](https://github.com/user-attachments/assets/58f5fc45-ce5e-4f4a-b1cd-81ae0cd23316)

```
sns.scatterplot(x=bala["Age"],y=bala["Fare"])
```
![Screenshot 2025-03-27 113108](https://github.com/user-attachments/assets/358d0257-aba0-46d6-a0d1-38e49ab060ea)

```
sns.jointplot(x="Age",y="Fare",data=bala)
```
![Screenshot 2025-03-27 113119](https://github.com/user-attachments/assets/7d94f364-a8ca-4a57-aa25-935c0f5b6ea0)
## Multivariate Analysis 
```
fig, ax1 = plt.subplots(figsize=(8,5))
plt = sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=bala)
```
![Screenshot 2025-03-27 113237](https://github.com/user-attachments/assets/889cc3e4-a856-45e5-b7c5-2e28c8438553)

```
sns.catplot(data=bala,col="Survived",x="Gender",hue="Pclass",kind="count")
```
![Screenshot 2025-03-27 113251](https://github.com/user-attachments/assets/19c7a1f9-5036-448c-be08-2ebcf68f7826)
## Co-relation
```
numerical_features = bala.select_dtypes(include=np.number)
corr = numerical_features.corr()
sns.heatmap(corr, annot=True)
```
![Screenshot 2025-03-27 113259](https://github.com/user-attachments/assets/ec7e4899-838d-45ab-b3d7-c9c3818881fa)

```
sns.pairplot(bala)
```
![Screenshot 2025-03-27 113547](https://github.com/user-attachments/assets/6c75134c-d7da-41e1-a329-0307538cbc0c)
![Screenshot 2025-03-27 113705](https://github.com/user-attachments/assets/20224427-94ec-4839-8460-a3fe8fc76e49)



# RESULT
We Have performed Exploratory Data Analysis on the given data set successfully 
