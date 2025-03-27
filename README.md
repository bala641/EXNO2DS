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
bala.set_index("PassengerId",inplace=True)
bala.describe()
```
![Screenshot 2025-03-27 112838](https://github.com/user-attachments/assets/a76c4f8d-f935-45bb-bf5a-1568d280fbf0)
```
bala.nunique()
```
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
bala.Pclass.unique()
```
![Screenshot 2025-03-27 112952](https://github.com/user-attachments/assets/f970de42-90d4-4502-b05f-28d2393f8747)

```
bala.rename(columns={'Sex':'Gender'},inplace=True)
bala
```
![Screenshot 2025-03-27 113010](https://github.com/user-attachments/assets/51d8a83f-d388-4f5a-9aa9-63a38c359de3)
```
sns.catplot(x="Gender",col="Survived",kind="count",data=bala,height=5,aspect=.7)
```
![Screenshot 2025-03-27 113028](https://github.com/user-attachments/assets/9df74e8d-9a8b-4823-bbc7-bb5d580a8d52)
```

```



# RESULl

        <<INCLUDE YOUR RESULT HERE>>
