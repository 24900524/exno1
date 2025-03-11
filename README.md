# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
```
NAME: DHARSHINI S N
REG NO: 212224230062
```
```
import pandas as pd
exp=pd.read_csv("/content/SAMPLEIDS.csv")
exp.head()
```
![image](https://github.com/user-attachments/assets/fe726ce4-0def-4e99-85ed-3f0792b9874d)
```
exp.head(5)
```
![image](https://github.com/user-attachments/assets/7ea868c5-d9c7-4695-bb2c-ec8b24f4ab67)
```
exp.tail(5)
```
![image](https://github.com/user-attachments/assets/97243524-f861-426f-8d67-04c34cc8236c)
```
exp.isnull().sum()
```
![image](https://github.com/user-attachments/assets/e66a91f5-1f6e-4c2f-9989-177cf1f2c4ef)
```
exp.isnull().any()
```
![image](https://github.com/user-attachments/assets/8761be88-d5d9-41cb-ab22-f83035d90823)
```
exp.dropna(axis=1)
```
![image](https://github.com/user-attachments/assets/c4093fe5-2100-440d-8d58-7be109f734fb)
![image](https://github.com/user-attachments/assets/425e974d-0707-419b-b004-e7898ef52ae6)
```
exp.fillna(50)
```
![image](https://github.com/user-attachments/assets/c99e06a9-c766-4c9f-9988-fc365f6f5d12)
![image](https://github.com/user-attachments/assets/a1535490-02d7-4950-8ba4-95356ab26439)
```
exp.fillna(method='ffill')
```
![image](https://github.com/user-attachments/assets/0970776b-1bbc-4619-ac70-4c5a030fdf52)
![image](https://github.com/user-attachments/assets/d552b751-2c96-46ad-8735-1a2c3554f0b7)
```
exp.fillna(method='bfill')
```
![image](https://github.com/user-attachments/assets/665c4a22-882e-45c1-ab9a-07431cc17b94)
```
lab.fillna({'GENDER':'MALE','NAME':'PRAKASH','ADDRESS':'POONAMALEE','M1':'50','M2':'89','M3':'75','M4':'82','TOTAL':'896','AVG':'89.00000'})
```
![image](https://github.com/user-attachments/assets/769e063a-d964-4b29-af0d-1e6bde62eedf)
```
exp=pd.read_csv("/content/iris.csv")
exp
```
![image](https://github.com/user-attachments/assets/8cf875cc-04fd-4d86-b069-8240fe702dc8)
```
lab.describe()
```
![image](https://github.com/user-attachments/assets/55157667-6bb6-49a0-9e6b-dea5567fc65b)
```
import seaborn as sns
sns.boxplot(x='sepal_width',data=lab)
```
![image](https://github.com/user-attachments/assets/42f729ef-3ba4-425b-947d-d015c57e9261)
```
q1=lab.sepal_width.quantile(0.25)
q3=lab.sepal_width.quantile(0.75)
iq=q3-q1
print(iq)
```
![image](https://github.com/user-attachments/assets/2c789bf3-df73-4698-87b9-55e69d629466)
```
rid=lab[((lab.sepal_width<(q1-1.5*iq))|(lab.sepal_width>(q3+1.5*iq)))]
rid['sepal_width']
```
![image](https://github.com/user-attachments/assets/5c9a8e29-8ba5-415b-a09e-982f1cc2b4ca)
```
depo=lab[~((lab.sepal_width<(q1-1.5*iq))|(lab.sepal_width>(q3+1.5*iq)))]
depo
```
![image](https://github.com/user-attachments/assets/43100756-6164-4ba2-b69e-54d26314ec6a)
```
sns.boxplot(x='sepal_width',data=depo)
```
![image](https://github.com/user-attachments/assets/5af31c87-59ff-4b04-a11d-ca76ef92a6bf)
```
import numpy as np
import scipy.stats as stats
z = np.abs(stats.zscore(lab.sepal_width))
z
```
![image](https://github.com/user-attachments/assets/a7119627-56f8-4709-aded-6cb2230c985c)
```
p=lab[z<2]
p
```
![image](https://github.com/user-attachments/assets/8442b676-e02e-4f5b-914a-78ab894d8c3a)


# Result

Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
