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
import seaborn as sns
df=pd.read_csv("/content/titanic_dataset.csv")
df
```
<img width="1273" height="467" alt="image" src="https://github.com/user-attachments/assets/c4351922-4623-408c-b601-866cb268a5c8" />

```
df.info()
```
<img width="390" height="344" alt="image" src="https://github.com/user-attachments/assets/1fd56e53-67a7-4610-8b93-5f6469feca51" />

```
df.describe()
```
<img width="794" height="302" alt="image" src="https://github.com/user-attachments/assets/79f6f47a-23d8-4d6c-aa8a-0e821a38fd87" />

```
df.dtypes
```
<img width="404" height="454" alt="image" src="https://github.com/user-attachments/assets/d667dcc7-0daf-4197-8ff6-0fe40a26545c" />

```
df.shape
```
<img width="1247" height="484" alt="image" src="https://github.com/user-attachments/assets/830cef81-d71e-4cdd-8d44-e0a7fa00c11b" />

```
df['Age'].value_counts()
```
<img width="539" height="489" alt="image" src="https://github.com/user-attachments/assets/7ed1d79e-34cb-4ed7-96ef-806dd5dccca8" />

```
df.set_index("PassengerId", inplace=True)
df
```
<img width="1201" height="457" alt="image" src="https://github.com/user-attachments/assets/374bcf40-2240-4f69-bf39-ac67e4aa610d" />

```
df.nunique()
```
<img width="456" height="428" alt="image" src="https://github.com/user-attachments/assets/bf9c3bf8-ba58-49dc-82f8-f498054102ea" />

```
sns.countplot(data=df,x="Age")
```
<img width="657" height="466" alt="image" src="https://github.com/user-attachments/assets/9bf0dfa5-42b3-4efd-b2f0-a8ba56f94ab1" />

```
df.rename(columns={'Sex':'Gender'},inplace=True)
df
```
<img width="1198" height="450" alt="image" src="https://github.com/user-attachments/assets/3c3df166-981d-4d31-a02a-0040ee35f30c" />

```
sns.catplot(x="Gender",col="Survived",kind="count",data=df)
```
<img width="1082" height="524" alt="image" src="https://github.com/user-attachments/assets/f7c71d8d-be5e-4fcf-bfe5-398f610624db" />

```
df.boxplot(column="Age",by="Survived")
```
<img width="633" height="492" alt="image" src="https://github.com/user-attachments/assets/8d5eac37-7019-444c-b7d8-dc8b03720bf8" />

```
sns.scatterplot(x=df["Age"],y=df["Fare"])
```
<img width="644" height="465" alt="image" src="https://github.com/user-attachments/assets/19f0fe6d-1a2b-4451-b722-f51a6fa59bd5" />

```
plt=sns.boxplot(x='Pclass',y='Age',hue='Gender',data=df)
```
<img width="646" height="444" alt="image" src="https://github.com/user-attachments/assets/2c8e2f4b-5892-4d86-b463-3d86678e4ee1" />

```
sns.catplot(x='Pclass',y='Age',hue='Gender',col='Survived',kind='box',data=df)
```
<img width="1153" height="522" alt="image" src="https://github.com/user-attachments/assets/003478a2-f7fd-44d2-a9b4-0b273d41458d" />

```
corr=df.corr(numeric_only=True)
sns.heatmap(corr,annot=True)
```
<img width="604" height="448" alt="image" src="https://github.com/user-attachments/assets/5c5fa5fa-6ac9-49ac-9be2-bf3096ce1083" />

# RESULT
Thus,the expriment- 'Exploratory Data Analysis' on the given data set was executed successfully.    
