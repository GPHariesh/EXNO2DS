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
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
<img width="1228" height="520" alt="Screenshot 2025-09-15 113030" src="https://github.com/user-attachments/assets/1a3e371b-edf5-4bf3-b640-aa8668b22355" />

```
df.info()
```

<img width="933" height="381" alt="Screenshot 2025-09-15 113039" src="https://github.com/user-attachments/assets/58cad9a9-ec73-4ab5-ba19-f20476c92dba" />


```
df.describe()
```
<img width="947" height="346" alt="Screenshot 2025-09-15 113355" src="https://github.com/user-attachments/assets/d2d8c005-50f4-44bb-b360-bc3c404f3779" />

```
df.dtypes
```
<img width="817" height="470" alt="Screenshot 2025-09-15 113401" src="https://github.com/user-attachments/assets/7cb8c803-93ba-4be0-948a-441cc429f33a" />


```
df.shape
```
<img width="835" height="89" alt="Screenshot 2025-09-15 113412" src="https://github.com/user-attachments/assets/c4e0a9d9-bc1b-4da8-ad95-f651dd5421e1" />

```
df.value_counts()
```
<img width="1278" height="493" alt="Screenshot 2025-09-15 113423" src="https://github.com/user-attachments/assets/61f47726-4a1d-4cfe-b5d0-69b9895f41a4" />


```
df['Age'].value_counts()
```
<img width="802" height="497" alt="Screenshot 2025-09-15 113433" src="https://github.com/user-attachments/assets/a8da88aa-d5d5-43b4-96fa-e7c791456c32" />


```
df.reset_index(inplace=True)
```
<img width="1418" height="566" alt="Screenshot 2025-09-15 113443" src="https://github.com/user-attachments/assets/9637489f-e0b3-4f0d-99ac-9f2ee184b838" />



```
df.set_index("PassengerId",inplace=True)
df
```

<img width="552" height="440" alt="Screenshot 2025-09-15 113453" src="https://github.com/user-attachments/assets/1fa08e6b-913f-47ce-986b-6ad84cf427b1" />


```
df.nunique()
```
<img width="552" height="440" alt="Screenshot 2025-09-15 113453" src="https://github.com/user-attachments/assets/c58da9b3-843a-45a7-9d43-179864711e71" />


```
sns.countplot(data=df,x='Age')
```

<img width="915" height="491" alt="Screenshot 2025-09-15 113459" src="https://github.com/user-attachments/assets/49dd0bc1-ff2f-48fa-842b-b3233d9df302" />



```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```

<img width="1303" height="514" alt="Screenshot 2025-09-15 113545" src="https://github.com/user-attachments/assets/86fa8189-7b85-4fdf-89a7-e1c093da3b9c" />

```
sns.catplot(data=df,x='Gender',col='Survived',kind='count')
```
<img width="1023" height="530" alt="Screenshot 2025-09-15 113552" src="https://github.com/user-attachments/assets/e940c979-6833-407b-bc67-6167f14038ce" />


```
df.boxplot(column='Age',by='Survived')
```
<img width="704" height="502" alt="Screenshot 2025-09-15 113557" src="https://github.com/user-attachments/assets/e203f5fa-e9d1-4d93-9a36-100307209810" />

sns.scatterplot(x=df['Age'],y=df['Fare'])

<img width="750" height="489" alt="Screenshot 2025-09-15 113601" src="https://github.com/user-attachments/assets/03524e00-f880-4bd7-8011-3c66dae10d6c" />

plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
<img width="738" height="454" alt="Screenshot 2025-09-15 113607" src="https://github.com/user-attachments/assets/ff7cdcd6-541f-4cfb-8f45-da026e1c0a0b" />

sns.catplot(x='Pclass',y='Age',hue='Gender',col='Survived',kind='box',data=df)
<img width="1069" height="511" alt="Screenshot 2025-09-15 113616" src="https://github.com/user-attachments/assets/9c6f990a-16aa-473e-afce-21560c2caba9" />

corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
<img width="610" height="486" alt="Screenshot 2025-09-15 113623" src="https://github.com/user-attachments/assets/d054bab4-abbc-4e9f-aa31-d181ed6bab52" />

corr=df.corr(numeric_only=True)
sns.heatmap(corr)
<img width="613" height="480" alt="Screenshot 2025-09-15 113628" src="https://github.com/user-attachments/assets/af2a4327-5ddf-408a-9891-4a321d871b61" />



# RESULT
Thus the Exploratory Data Analysis on the given data set is performed successfully.
