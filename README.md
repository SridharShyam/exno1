# Exno - 1: Data Cleaning Process

# AIM:

To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation:

Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm:

STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output:
Reg.No: 212223240156
Developed by: SHYAM S

```

import pandas as pd
import numpy as np
import seaborn as sns

df=pd.read_csv("SAMPLEIDS.csv")
df.head(10)

![image](https://github.com/user-attachments/assets/7a9c66f7-0e51-4cc2-8245-b85d3e575808)

df.tail(10)

![image](https://github.com/user-attachments/assets/bf016f37-e193-410e-94a5-b83f1f919866)

df.info()

![image](https://github.com/user-attachments/assets/9febd065-b5eb-445e-99f4-aed95d30a2a7)

df.describe()

![image](https://github.com/user-attachments/assets/58530806-7645-4305-9aa5-93b2bc599175)

df.dropna()

![image](https://github.com/user-attachments/assets/de6903b3-0841-4ced-b8b2-d82fbc842ff7)

new_df=df.fillna(method="ffill")
new_df

![image](https://github.com/user-attachments/assets/bf277316-e1c2-44c9-b03f-5bdaf2fa3015)

new_df=df.fillna(method="bfill")
new_df

![image](https://github.com/user-attachments/assets/26158ddd-fa01-42e5-89b6-5eb88067d983)

new_df=new_df.drop(columns=["SNO","REGNO","NAME","DOB","GENDER","ADDRESS"])
new_df

![image](https://github.com/user-attachments/assets/2e1a3333-b825-410e-bcab-d696204500b9)

sns.boxplot(data=new_df)

![image](https://github.com/user-attachments/assets/4d0a0943-8686-4353-bd10-3b30d6d92dad)

sns.boxenplot(data=new_df)

![image](https://github.com/user-attachments/assets/4851811c-235f-4818-99de-db4737f9edb9)

sns.scatterplot(data=new_df)

![image](https://github.com/user-attachments/assets/10b0d5f2-0c80-4025-bb32-cfebe76e473f)

![image](https://github.com/user-attachments/assets/7e9a3368-b731-4e01-b724-89b622680f01)

Q1=np.percentile(new_df,25)
Q3=np.percentile(new_df,75)
IQR=Q3-Q1
IQR

![image](https://github.com/user-attachments/assets/d806cb92-e048-4da4-8ea1-9feaae25a9ea)

lower_bound=Q1-2*IQR
lower_bound

![image](https://github.com/user-attachments/assets/7d2d6991-56ca-4aff-8442-206d2557f250)

upper_bound=Q3+2*IQR
upper_bound

![image](https://github.com/user-attachments/assets/de90b512-7832-4ba1-b202-5e7a4a4064b2)

outliers = new_df[(new_df < lower_bound) | (new_df > upper_bound)]
outliers

![image](https://github.com/user-attachments/assets/30ec74c4-2b08-4094-902d-06ca0115a104)

print("Q1:",q1)
print("Q3:",q3)
print("IQR:",IQR)
print("Lower Bound:",lower_bound)
print("Upper Bound:",upper_bound)
print("Outliers:",outliers)

![image](https://github.com/user-attachments/assets/05cb61af-0700-41de-bb46-722237a18fc2)

sns.boxplot(data=new_df)

![image](https://github.com/user-attachments/assets/c0e637f4-90c9-4f6d-9a62-ea840dd3d18d)

sns.boxenplot(data=new_df)

![image](https://github.com/user-attachments/assets/343b0f10-9ddb-4ce7-8a4f-3a688d956410)

sns.scatterplot(data=new_df)

![image](https://github.com/user-attachments/assets/d0b4a8b4-0e3a-4f1c-974c-8b8ea593d711)

```

# Result:

The dataset has been cleaned, and outliers have been successfully removed.
