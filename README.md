
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

# Coding and Output:
~~~~
import pandas as pd
df=pd.read_csv('/content/Data_set (1).csv')
df
~~~~
<img width="1557" height="605" alt="Screenshot 2025-08-26 221618" src="https://github.com/user-attachments/assets/9fa740a8-4772-460c-ad57-6c1c8374836e" />



df.info() 

<img width="845" height="417" alt="Screenshot 2025-08-26 222226" src="https://github.com/user-attachments/assets/5ddd6778-e0c9-453c-ac18-788da9c8655a" />


df.describe()

<img width="1077" height="424" alt="Screenshot 2025-08-26 222403" src="https://github.com/user-attachments/assets/9b80fe67-39fe-4777-8469-33e48858154c" />


df.head(10)

<img width="1618" height="503" alt="Screenshot 2025-08-26 222512" src="https://github.com/user-attachments/assets/2de7d707-636f-49ee-b45b-d5c7974e4002" />


df.tail(5)

<img width="1529" height="303" alt="Screenshot 2025-08-26 222608" src="https://github.com/user-attachments/assets/3451e0dc-f6eb-4f10-8783-cc0ccb461e18" />


df.shape

<img width="1422" height="100" alt="Screenshot 2025-08-26 222704" src="https://github.com/user-attachments/assets/40ac5043-edae-404c-b900-ee612c48df39" />


   
df.isnull()

<img width="1367" height="572" alt="Screenshot 2025-08-26 222744" src="https://github.com/user-attachments/assets/8b923ed5-c49b-4001-b966-df52ac10a75d" />


df.notnull()

<img width="1366" height="568" alt="Screenshot 2025-08-26 223234" src="https://github.com/user-attachments/assets/a60e1edd-3efd-4589-80fa-445c3438a7e6" />


df.isnull().sum()

<img width="392" height="504" alt="Screenshot 2025-08-26 223415" src="https://github.com/user-attachments/assets/9560e974-9979-4d44-a8a6-64564127f90f" />


df.dropna(axis=0)

<img width="1651" height="567" alt="image" src="https://github.com/user-attachments/assets/a69ad5b7-c3fd-4ed4-8937-814c5f28df5c" />


df.dropna(axis=1)

<img width="655" height="577" alt="Screenshot 2025-08-27 190800" src="https://github.com/user-attachments/assets/fd940582-9660-4000-ba30-31c824953444" />

~~~
dfs=df[df['num_episodes']>20]
dfs
~~~
<img width="733" height="71" alt="Screenshot 2025-08-27 190940" src="https://github.com/user-attachments/assets/e05695dd-df10-4b47-990e-9b00340087f1" />

<img width="1818" height="920" alt="Screenshot 2025-08-27 191037" src="https://github.com/user-attachments/assets/52e49ee4-e3d9-4d32-842f-2741a12a597c" />


df.fillna(0)

<img width="1564" height="579" alt="Screenshot 2025-08-27 191142" src="https://github.com/user-attachments/assets/065e8c28-2902-4521-a069-76bb9320b1f4" />

~~~~
dfs=df[df['show_name'].str.startswith(('A','F'))&(df['num_episodes']>25)]
dfs
~~~~
<img width="1594" height="204" alt="Screenshot 2025-08-27 191703" src="https://github.com/user-attachments/assets/495066c6-1644-4df4-9eda-ad34840954ec" />


df.iloc[:3]

<img width="1551" height="240" alt="Screenshot 2025-08-27 191814" src="https://github.com/user-attachments/assets/79ae9d44-2fc9-4817-886c-83d1d395eac5" />


df.iloc[:4]

<img width="1536" height="274" alt="Screenshot 2025-08-27 191931" src="https://github.com/user-attachments/assets/0947dc9c-53f4-4fa3-972a-613650d9a4db" />


df.iloc[[1,3,5],[1,3,5]]

<img width="1288" height="248" alt="Screenshot 2025-08-27 192052" src="https://github.com/user-attachments/assets/f658db78-645b-4d70-a8d1-79ab7566ad6a" />


df.fillna('sample value')

<img width="1622" height="572" alt="Screenshot 2025-08-27 192217" src="https://github.com/user-attachments/assets/c68e85f8-c2b7-410a-906f-4d0548077e3b" />

~~~~
ffil=df.fillna(method='ffill')
ffil
~~~~
<img width="1731" height="639" alt="Screenshot 2025-08-27 192321" src="https://github.com/user-attachments/assets/9c846a8f-a4a0-4c31-83f6-b04159e20368" />

~~

bfil=df.fillna(method='bfill')
bfil

~~

<img width="1705" height="635" alt="Screenshot 2025-08-27 192450" src="https://github.com/user-attachments/assets/52871cae-a849-4f2a-8b31-858a27cb000c" />

~~~
m=df.num_episodes.mean()
m
~~~
<img width="1168" height="120" alt="Screenshot 2025-08-27 192538" src="https://github.com/user-attachments/assets/f395a0e6-42a6-4257-af38-170b15704a7c" />

~~~
m= df.fillna(df['num_episodes'].mean())
m
~~~
<img width="1583" height="592" alt="Screenshot 2025-08-27 192645" src="https://github.com/user-attachments/assets/920378da-a4bc-48ae-81cd-d601bbf48d7f" />

~~~
fmean=df['lifetime_popularity_rank'].fillna(value=df['lifetime_popularity_rank'].mean())
fmean
~~~
<img width="1176" height="648" alt="Screenshot 2025-08-27 192741" src="https://github.com/user-attachments/assets/cca99f1f-e9ae-42ae-b81c-7421595637f0" />

~~
df=pd.read_csv('/content/SAMPLEIDS.csv')
df
``~~
<img width="1112" height="934" alt="Screenshot 2025-08-27 192825" src="https://github.com/user-attachments/assets/2bde1619-95c1-477b-90c1-b1fed03fcb7d" />


df.shape

<img width="1103" height="92" alt="Screenshot 2025-08-27 192908" src="https://github.com/user-attachments/assets/d2f2bfac-6f45-4c6b-954a-24da008b4bab" />


df.describe()

<img width="1020" height="431" alt="Screenshot 2025-08-27 192958" src="https://github.com/user-attachments/assets/0d372107-9b8d-486e-8697-dfa76f56d9de" />


df.info()

<img width="823" height="494" alt="Screenshot 2025-08-27 193043" src="https://github.com/user-attachments/assets/beb9974a-0fa1-4730-bc99-e14ddc893bbb" />


df['GENDER'].value_counts()

<img width="478" height="276" alt="Screenshot 2025-08-27 193138" src="https://github.com/user-attachments/assets/ee363604-6326-4028-8259-e234f656157d" />


df.dropna(how='any').shape

<img width="712" height="107" alt="Screenshot 2025-08-27 193229" src="https://github.com/user-attachments/assets/8d5882e9-f9ac-4d49-bf00-f0b27bdab627" />

~~
x1=df.dropna(how='any')
x1

<img width="1126" height="646" alt="image" src="https://github.com/user-attachments/assets/6c9fd0f7-0b03-4c19-9a1b-2f15879e290b" />

~~

res=df.dropna(subset=['M1','M2','M3','M4'],how='any')
res

<img width="1103" height="635" alt="Screenshot 2025-08-27 193419" src="https://github.com/user-attachments/assets/8726852f-25bc-45fe-8483-3b69398f34fe" />

~~

m2=df.TOTAL.mean()
m2

~~

<img width="1069" height="119" alt="Screenshot 2025-08-27 193509" src="https://github.com/user-attachments/assets/8d35ce76-e384-4a29-9e64-5d4116cff2dc" />

df.TOTAL.fillna(m2,inplace=False)

<img width="921" height="925" alt="Screenshot 2025-08-27 193601" src="https://github.com/user-attachments/assets/802bc461-37b2-4d5d-932c-5f177b89c38e" />


df.isnull()

<img width="935" height="923" alt="Screenshot 2025-08-27 201005" src="https://github.com/user-attachments/assets/3e96702e-2bdc-4938-93c8-b584f3f2cf30" />

~~

import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=False,annot=True)

~~

<img width="816" height="708" alt="Screenshot 2025-08-27 201133" src="https://github.com/user-attachments/assets/9fb3e20d-d39e-4b20-a64d-b48405ea8250" />


~~

import seaborn as sns
sns.heatmap(df.isnull(),yticklabels=True,annot=True)

~~

<img width="722" height="707" alt="Screenshot 2025-08-27 201323" src="https://github.com/user-attachments/assets/58385887-9dc3-4485-968d-e2c3226728ed" />

~~

df.dropna(inplace=True)
sns.heatmap(df.isnull(),yticklabels=False,annot=True)

~~

<img width="748" height="701" alt="Screenshot 2025-08-27 201426" src="https://github.com/user-attachments/assets/604bb13b-f04e-4dc1-a6f4-40708c733b5a" />

~~


import scipy.stats as stats
df=pd.read_csv("/content/heights.csv")
df

~~

<img width="658" height="705" alt="Screenshot 2025-08-27 201506" src="https://github.com/user-attachments/assets/68174210-0064-400b-ae08-21af94261d95" />


sns.boxplot(data=df)

<img width="856" height="622" alt="Screenshot 2025-08-27 201549" src="https://github.com/user-attachments/assets/1e85a0fc-8dac-427f-b7e1-3966364d0a77" />


sns.scatterplot(data=df)

<img width="877" height="600" alt="Screenshot 2025-08-27 201800" src="https://github.com/user-attachments/assets/b516273d-e9b3-4fbb-b020-04a9d042d0d0" />

~~

max=df['height'].quantile(0.75)
min=df['height'].quantile(0.25)
iqr=max-min
iqr

~~

<img width="1145" height="187" alt="Screenshot 2025-08-27 201838" src="https://github.com/user-attachments/assets/dc566acd-8d66-4c58-bcff-d89ee274ac9f" />

~~

 lb=min-1.5*iqr
ub=max+1.5*iqr
outliers=df[(df['height']<lb)|(df['height']>ub)]
print("Lower bound:",lb)
print("Upper bound:",ub)
print("Outliers:",outliers)

~~

<img width="1048" height="316" alt="Screenshot 2025-08-27 202221" src="https://github.com/user-attachments/assets/84976a45-3c9c-467c-ada7-e1290b4e3bc4" />

~~

no_outliers=df[~((df['height']<lb)|(df['height']>ub))]
no_outliers

~~

<img width="619" height="624" alt="Screenshot 2025-08-27 202756" src="https://github.com/user-attachments/assets/3f466fac-f096-406d-b72e-5bee815c308b" />


sns.boxplot(data=no_outliers)

<img width="910" height="632" alt="Screenshot 2025-08-27 203019" src="https://github.com/user-attachments/assets/30ecc3a3-358d-4979-a88f-a8082551cc9e" />


sns.scatterplot(data=no_outliers)

<img width="934" height="614" alt="Screenshot 2025-08-27 203112" src="https://github.com/user-attachments/assets/96033f0e-45f2-40ce-8ead-f9a0b8f3b318" />


~~

import matplotlib.pyplot as plt
df
~~

<img width="685" height="681" alt="Screenshot 2025-08-27 203303" src="https://github.com/user-attachments/assets/e4240d80-8dbb-4a0d-9920-230dadac53d7" />

~~

max=df['height'].quantile(0.75)
q2=df['height'].quantile(0.5)
min=df['height'].quantile(0.25)
iqr=max-min
lb=min-1.5*iqr
ub=max+1.5*iqr
dfs=df[(df['height']>=lb)&(df['height']<=ub)]
dfs

~~

<img width="934" height="761" alt="Screenshot 2025-08-27 203357" src="https://github.com/user-attachments/assets/d4fe0a52-c6b6-4a37-b057-9f94577f1827" />

~~

import numpy as np
z=np.abs(stats.zscore(df['height']))
z
~~

<img width="888" height="182" alt="Screenshot 2025-08-27 203619" src="https://github.com/user-attachments/assets/41812a33-0591-42ad-89ba-c45c7dda27e1" />

~~
df1=df[z<3]
df1
~~

<img width="544" height="682" alt="image" src="https://github.com/user-attachments/assets/d5db12ca-81dd-4b8b-8363-ae423ef3d4d9" />



~~
val=df['height']
val
~~


<img width="703" height="731" alt="Screenshot 2025-08-27 203757" src="https://github.com/user-attachments/assets/0d2687a3-44f0-494a-9d9a-96a04aabdbd2" />



~~
out=[]
def d_o(val):
  ts=3
  m=np.mean(val)
  sd=np.std(val)
  for i in val:
    z=(i-m)/sd
    if np.abs(z)>ts:
      out.append(i)
  return out
~~



<img width="962" height="345" alt="Screenshot 2025-08-27 203842" src="https://github.com/user-attachments/assets/e4e1be24-ed0f-4bd3-a23a-17d6946ad55b" />


 op

<img width="966" height="114" alt="Screenshot 2025-08-27 204101" src="https://github.com/user-attachments/assets/255a7274-417b-43d9-84ae-afbbddb35b6e" />




# Result#:

Thus we have cleaned the data and removed and the outliers by detection using IQR and Z- score method
