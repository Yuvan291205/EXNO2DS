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
![image](https://github.com/user-attachments/assets/d1da02bc-001f-4090-851b-2420fd7fbfc4)
```
df.info()
```
![image](https://github.com/user-attachments/assets/4b6afa63-5d61-44b3-9244-45f58c8e71b6)
```
df.shape
```
![image](https://github.com/user-attachments/assets/31f95fae-e506-4e58-9700-8a0389e6dbca)
```
import pandas as pd
df=pd.read_csv("/content/titanic_dataset.csv")
df.set_index("PassengerId",inplace=True)
print(df.set_index)
```
![image](https://github.com/user-attachments/assets/7e909a19-6b8e-4eae-858c-22286a274992)
```
df.describe()
```
![image](https://github.com/user-attachments/assets/eed15731-6226-43aa-a179-624a4048ede1)
```
df.nunique()
```
![image](https://github.com/user-attachments/assets/1800e564-c2e0-4e21-b58e-8692f7e0181f)
```
df["Survived"].value_counts()
```
![image](https://github.com/user-attachments/assets/5ed04868-66ba-45ea-9942-2028097252f9)
```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```
![image](https://github.com/user-attachments/assets/5a6d5d87-c442-415d-9f5b-6a3a6c7dd93f)
```
sns.countplot(data=df,x="Survived")
```
![image](https://github.com/user-attachments/assets/f7e3eb16-a0ea-4a3b-be78-6f301d2b6763)
```
df
```
![image](https://github.com/user-attachments/assets/8bcc8340-af70-439a-bbe9-47a4f546b5c9)
```
df.rename(columns={'sex':'Gender'},inplace=True)
df
```
![image](https://github.com/user-attachments/assets/64797c4d-c1ea-411d-ae3f-47657bbc9871)
```
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
sns.catplot(x="Sex",col='Survived',kind="count",data=df,height=5, aspect=.7)
```
![image](https://github.com/user-attachments/assets/e93fbbde-4e0a-49d7-a9fd-f5a79fcd9a53)
```
sns.catplot(x='Survived',hue='Sex',data=df,kind='count')
```
![image](https://github.com/user-attachments/assets/245871a4-5fb9-4fd9-a226-b4fac517b099)
```
df.boxplot(column='Age',by="Survived")
```
![image](https://github.com/user-attachments/assets/78f6b75d-da45-47de-8eda-e23b9ba0a775)
```
sns.scatterplot(x=df['Age'],y=df["Fare"])
```
![image](https://github.com/user-attachments/assets/cfde6ee8-95ad-4e91-a9f7-13746cb13683)
```
import matplotlib.pyplot as plt
fig,ax1=plt.subplots(figsize=(8,5))
pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Sex',data=df)
```
![image](https://github.com/user-attachments/assets/49af67d6-304d-4fba-b910-31d8521241be)
```
sns.catplot(data=df,col='Survived',x='Sex',hue='Pclass',kind='count')
```
![image](https://github.com/user-attachments/assets/493011a7-d5e5-4fa6-9f0d-30a245c090c0)
```
import seaborn as sns
corr=df.corr()
sns.heatmap(corr,annot=True)
```
![image](https://github.com/user-attachments/assets/292398a9-0836-4cca-b4ab-dd9d95185556)
```
sns.pairplot(df)
```
![image](https://github.com/user-attachments/assets/7587325b-eb3e-4bf0-b8b8-38f3800eddfc)


# RESULT
          Thus the data analysis has been implemented succesfully.
