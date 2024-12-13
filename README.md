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
 from google.colab import drive
drive.mount('/content/drive')

import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

ls drive/MyDrive/titanic_dataset.csv

df=pd.read_csv('drive/MyDrive/titanic_dataset.csv')
df

![Screenshot 2024-12-13 202630](https://github.com/user-attachments/assets/9d6cf6af-fcb9-49e3-a2ab-8741d0a8d245)

df.info()

![Screenshot 2024-12-13 202644](https://github.com/user-attachments/assets/e3de3ca4-3e77-4653-a950-1d8d5a90bc13)

df.set_index('PassengerId',inplace=True)

df.describe()

![Screenshot 2024-12-13 202658](https://github.com/user-attachments/assets/60ee85a9-736a-40e2-b100-4c1a9171bee6)

df.shape

![Screenshot 2024-12-13 202707](https://github.com/user-attachments/assets/caff975f-235c-4dbc-8098-b91586bedf21)

df.nunique()

![Screenshot 2024-12-13 202714](https://github.com/user-attachments/assets/f169629f-2ab5-444f-9c73-94f68ceaaf68)

df['Survived'].value_counts()

![Screenshot 2024-12-13 202725](https://github.com/user-attachments/assets/e2d8dcd2-140e-4320-b039-c2ec202187d0)

per=(df['Survived'].value_counts()/df.shape[0]*100).round(2)

per

![Screenshot 2024-12-13 202735](https://github.com/user-attachments/assets/5170f8d1-4e87-48d6-b6fc-d3e94ef89c43)


sns.countplot(data=df,x='Survived')

![Screenshot 2024-12-13 202746](https://github.com/user-attachments/assets/ebf83750-c4b7-4d63-8346-ee03f9c7c3ac)

df

![Screenshot 2024-12-13 202800](https://github.com/user-attachments/assets/5f8cb462-9a48-4327-89ff-6ade8b537784)

df.Pclass.unique()

![Screenshot 2024-12-13 202813](https://github.com/user-attachments/assets/a391de10-b1af-4447-8492-19ca72e2626a)

df.rename(columns={'Sex':'Gender'},inplace=True)

sns.catplot(x='Gender',col='Survived',kind='count',data=df,height=5,aspect=.7)

![Screenshot 2024-12-13 202831](https://github.com/user-attachments/assets/c7374454-6b84-4059-9b70-f2d134427f38)

sns.catplot(x='Survived',hue='Gender',data=df,kind='count')

![Screenshot 2024-12-13 202856](https://github.com/user-attachments/assets/4693d734-a8ce-4313-a2fc-cca9082c7a62)

df.boxplot(column='Age',by='Survived')

![Screenshot 2024-12-13 202912](https://github.com/user-attachments/assets/87f214b9-6d6f-490f-9b47-18182b361cc4)

sns.scatterplot(x=df['Age'],y=df['Fare'])

![Screenshot 2024-12-13 202922](https://github.com/user-attachments/assets/e817e95b-bb0b-4865-9b67-4c4b37793e2a)

fig,ax1=plt.subplots(figsize=(8,5))

pt=sns.boxplot(ax=ax1,x='Pclass',y='Age',hue='Gender',data=df)

![Screenshot 2024-12-13 202933](https://github.com/user-attachments/assets/ce97dddd-2b89-4b33-ae40-f232ac957b03)

sns.catplot(data=df,col='Survived',x='Gender',hue='Pclass',kind='count')

![Screenshot 2024-12-13 203020](https://github.com/user-attachments/assets/d3e612c1-5d89-4e9a-8712-a0c9142ca138)

numeric_df=df.select_dtypes(include=np.number)
corr=numeric_df.corr()
sns.heatmap(corr,annot=True)

![Screenshot 2024-12-13 203037](https://github.com/user-attachments/assets/06680d9d-12a0-43cf-9168-3529ac168af4)

sns.pairplot(df)

![WhatsApp Image 2024-12-13 at 20 39 58_f88cc627](https://github.com/user-attachments/assets/647921e8-4353-4e7f-8bb5-a314ecd7ecc4)

# RESULT
  The code is run sucessfully.

