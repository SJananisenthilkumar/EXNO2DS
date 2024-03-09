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
import numpy as  np
import matplotlib.pyplot as plt
import seaborn as sns
```
```
dt=pd.read_csv("/content/titanic_dataset.csv")
dt
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/44837fa1-c10a-4bc7-8cfe-c056f7c9e011)

```
dt.info()
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/0d7b170a-bd98-438f-bafe-533d561cef8b)

```
dt.describe()
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/cad2f839-f01b-46ee-be01-f7d690eafe00)

```
dt.shape
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/ad9a98a7-160a-453b-a4c9-40eb6e684190)

```
dt.nunique()
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/af4e7240-bf4a-48ea-9890-fef42fc2276f)

```
dt["Survived"].value_counts()
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/a764fa03-7b4a-4c5b-b614-2ca37b3809a8)

```
per=(dt["Survived"].value_counts()/dt.shape[0]*100).round(2)
per
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/3801d4c1-2517-4bab-bee6-babf70e95ae4)

```
sns.countplot(data=dt,x="Survived")
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/f7065180-260d-4ae8-b468-9b93f8710859)

```
dt
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/071827ee-d822-440b-b168-67421281f0c6)

```
dt.Pclass.unique()
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/3ee03280-17da-44e7-903f-dfde041991a8)

```
dt.rename(columns = {'Sex':'Gender'},inplace = True)
dt
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/29dd699f-b7e0-4362-bfa7-b879bf7b7112)

```
sns.catplot(x="Gender",col="Survived",kind="count",data=dt,height=5,aspect=.7)
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/e4ce3cba-b27f-4894-9c4a-7b5229b650f5)

```
sns.catplot(x='Survived',hue="Gender",data=dt,kind = "count")
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/9c5941b7-104e-4597-8918-c27edfcecaa5)

```
dt.boxplot(column="Age",by="Survived")
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/21c9d69b-76a7-4b6d-a962-0b1d068c59cd)

```
sns.scatterplot(x=dt["Age"],y=dt["Fare"])
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/b8da3797-0302-4cfd-a734-c3dff6831771)

```
sns.jointplot(x="Age",y="Fare",data=dt)
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/7ce946da-9ba4-4a36-8009-215404da79b7)

```
fig, ax1 = plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x= 'Pclass',y='Age', hue='Gender',data=dt)
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/239b4aa6-b177-4d56-bd67-21d036d62a8a)

```
sns.catplot(data=dt,col = "Survived",x = "Gender", hue="Pclass",kind = "count")
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/c21a4a0d-f960-4aa9-ad8e-c221dc4813f0)

```
corr=dt.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/da868424-1938-47a9-8a50-17fc3100d41b)

```
sns.pairplot(dt)
```
![image](https://github.com/SJananisenthilkumar/EXNO2DS/assets/144871139/f19808aa-1c27-4bba-b33b-fd324bc68414)

# RESULT
Thus the Exploratory Data Analysis process is performed successfully on the given data using python code.
