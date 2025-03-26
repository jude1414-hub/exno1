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
            import pandas as pd
            df=pd.read_csv("/content/SAMPLEIDS.csv")
            df
![image](https://github.com/user-attachments/assets/668af798-483a-4078-b77e-fc02bc6f6333)
            df.isnull().sum()
![419080584-56422d77-1b6f-42a4-aa99-4f02a6da47a1](https://github.com/user-attachments/assets/afcae269-76ff-4167-b21e-8573eea545d5)
            df.isnull().any()<br>
![image](https://github.com/user-attachments/assets/5e1b9f5c-e9fa-4b0f-a54b-f64871db2a8d)
            df.dropna()
![image](https://github.com/user-attachments/assets/d1dd9286-d86e-48e9-80b2-8377386a05ba)
            df.fillna(0)
![image](https://github.com/user-attachments/assets/964d98b3-4c8f-4579-ae40-a8b8d1058e36)
            df.fillna(method='ffill')
![image](https://github.com/user-attachments/assets/5e7635d4-832e-4d8f-b104-196e552ac4d5)
            df.fillna(method='bfill')
![image](https://github.com/user-attachments/assets/66935750-4de7-48c8-ad8b-9fdb783eac31)
            df_dropped = df.dropna()
            df_dropped
![image](https://github.com/user-attachments/assets/db139d77-e358-4787-94cd-8e6041e2353e)
            df.fillna({'GENDER':'MALE','NAME':'SRI','ADDRESS':'POONAMALEE','M1':98,'M2':87,'M3':76,'M4':92,'TOTAL':305,'AVG':89.999999})
![image](https://github.com/user-attachments/assets/be8c41bb-bd1d-4356-bcf8-c7f1ab19ac04)
            ir=pd.read_csv("/content/iris.csv")
            ir
![image](https://github.com/user-attachments/assets/7ac44d83-56e3-4f07-99a8-388491324c4f)
            ir.describe()
![image](https://github.com/user-attachments/assets/c8719509-dc8c-4970-a584-d1ab13cae2d8)
            import seaborn as sns
            sns.boxplot(x='sepal_width',data=ir)
![image](https://github.com/user-attachments/assets/51ae5209-d8ba-4b5a-8dbb-b9744fd1c765)

                        q1=ir.sepal_width.quantile(0.25)
                        q3=ir.sepal_width.quantile(0.75)
                        iq=q3-q1
                        print(q3)
                        rid=ir[((ir.sepal_width<(q1-1.5*iq))|(ir.sepal_width>(q3+1.5*iq)))]
                        rid['sepal_width']
                        
![image](https://github.com/user-attachments/assets/53c8963d-07e9-4040-8235-ef29222daf1d)
            delid=ir[~((ir.sepal_width<(q1-1.5iq))|(ir.sepal_width>(q3+1.5iq)))] delid
![image](https://github.com/user-attachments/assets/84ff41eb-1143-494c-af13-ec0a69e2d87b)
            sns.boxplot(x='sepal_width',data=delid)
![image](https://github.com/user-attachments/assets/3a89a905-f64b-477e-96ec-bc37c9fae52f)
            import matplotlib.pyplot as plt
            import pandas as pd
            import numpy as np
            import scipy.stats as stats
            ``
            
            dataset=pd.read_csv("heights.csv")
            dataset
![image](https://github.com/user-attachments/assets/e686d2a6-dbe8-4610-bfd4-8453e65ab565)
            df = pd.read_csv("heights.csv")
            q1 = df['height'].quantile(0.25)
            q2 = df['height'].quantile(0.5)
            q3 = df['height'].quantile(0.75)
            ``
            
            iqr = q3-q1
            iqr
![image](https://github.com/user-attachments/assets/7ccc53d1-6e48-4798-b9d5-443a7c532e79)
            low = q1- 1.5*iqr
            low
![image](https://github.com/user-attachments/assets/797ad9fa-9167-4dbb-a3a9-0ae986f70cac)
            high = q3 + 1.5*iqr
            high
![image](https://github.com/user-attachments/assets/ecd4b83b-f15c-4170-a1d5-ae325e2f7f4c)
            df1 = df[((df['height'] >=low)& (df['height'] <=high))]
            df1
![image](https://github.com/user-attachments/assets/35d7a404-a363-4835-8664-0a8a1e7164af)
            z = np.abs(stats.zscore(df['height']))
            z
![image](https://github.com/user-attachments/assets/0d2330dc-63df-4cab-877c-fad486cae9ab)
            df1 = df[z<3]
            df1
![image](https://github.com/user-attachments/assets/7502b321-528f-4392-9a0a-cf7fbcbf0bc0)




# Result
          <<include your Result here>>
