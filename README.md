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

# Coding and Output:
import pandas as pd
df=pd.read_csv('/content/Data_set (1).csv')
df
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














# Result
          <<include your Result here>>
