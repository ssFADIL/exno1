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
import pandas as pd
science=pd.read_csv("/content/SAMPLEIDS.csv")
science
```
<img width="907" height="705" alt="image" src="https://github.com/user-attachments/assets/71640e04-5afb-44a7-84e1-7b258984e5b6" />



```
science.head()
```
<img width="1496" height="267" alt="image" src="https://github.com/user-attachments/assets/3191e9f1-3fe6-4e7c-b8eb-b252ee13b828" />


```
science.tail()
```
<img width="1498" height="218" alt="image" src="https://github.com/user-attachments/assets/ed844907-9df3-4e5f-8cb4-c1cef49cac0f" />


```
science.info()
```
<img width="1497" height="339" alt="image" src="https://github.com/user-attachments/assets/4c9b9a82-0e74-4d79-8297-d204c5c7c434" />


```
science.describe()
```
<img width="1497" height="322" alt="image" src="https://github.com/user-attachments/assets/959bf06e-0d35-4516-8576-eb04cb44f6a0" />


```
science.isnull().sum()
```
<img width="1486" height="460" alt="image" src="https://github.com/user-attachments/assets/7aa9c029-4d0f-4a06-b25e-eb9109e3f19c" />


```
science.notnull()
```
<img width="1498" height="677" alt="image" src="https://github.com/user-attachments/assets/3c784769-4ae4-454c-bac1-e2caf7b0d57c" />

```
science.dropna()
```
<img width="1495" height="448" alt="image" src="https://github.com/user-attachments/assets/0fe8a8cd-70e0-4946-b32b-4ab4fdc1290b" />


```
science.fillna(10)
```
<img width="1487" height="672" alt="image" src="https://github.com/user-attachments/assets/77bc1539-a74f-46a8-aada-266f86fcc073" />



```
science.fillna(method='ffill')
```
<img width="1488" height="700" alt="image" src="https://github.com/user-attachments/assets/87ead010-2ede-4235-8b70-913343176e90" />




```
science.fillna(method='bfill')
```

<img width="1478" height="694" alt="image" src="https://github.com/user-attachments/assets/31bbdb5c-6561-4927-ae5c-207e9b0ebe12" />


```
science.fillna({'GENDER':'MALE','NAME':'SAM'})
```


<img width="1489" height="669" alt="image" src="https://github.com/user-attachments/assets/6821c17b-a39a-4246-899d-4c1c3219dfd9" />


```
iris=pd.read_csv("/content/iris.csv")
iris
```

<img width="1487" height="497" alt="image" src="https://github.com/user-attachments/assets/a4ec6b07-b07a-4f3e-8f3d-310ed2f1ec94" />




```
iris.head()
```

<img width="1052" height="263" alt="image" src="https://github.com/user-attachments/assets/ed48a6de-6b0e-419a-84ae-1f25b06f4500" />


```
iris.tail()
```

<img width="1100" height="226" alt="image" src="https://github.com/user-attachments/assets/7a1b5ca7-76ab-4889-bd0d-4b0ac5584b9a" />



```
iris.info()
```
<img width="913" height="239" alt="image" src="https://github.com/user-attachments/assets/1a66d6fe-93c5-4448-a0cb-1b213e15d6e3" />




```

iris.describe()
```
<img width="1090" height="328" alt="image" src="https://github.com/user-attachments/assets/c4dedea0-e3dc-444c-a273-53376c546bd7" />


```
iris.isnull().sum()
```
<img width="841" height="247" alt="image" src="https://github.com/user-attachments/assets/f99f1398-5c36-409e-bea0-4ea9e4e75c25" />



```
iris.isnull().any()
```
<img width="839" height="250" alt="image" src="https://github.com/user-attachments/assets/89d4773f-7d13-4446-9743-0055aea925dc" />



```
iris.notnull()
```

<img width="846" height="412" alt="image" src="https://github.com/user-attachments/assets/ef6f7044-4cb2-4808-837a-ab37c0738fb8" />

```
iris.dropna()
```

<img width="856" height="419" alt="image" src="https://github.com/user-attachments/assets/3126a9f4-e6f3-4c5d-a362-24f009b9847a" />


```
iris.dropna(axis=1)
```

<img width="957" height="412" alt="image" src="https://github.com/user-attachments/assets/a9292452-794c-40d5-a757-574e5053fcb1" />

```
iris.fillna(8)
```
<img width="953" height="413" alt="image" src="https://github.com/user-attachments/assets/eff4d7f2-c9eb-4170-bc20-85810f0d1e29" />


```
iris.fillna(method='ffill')
```
<img width="1046" height="448" alt="image" src="https://github.com/user-attachments/assets/4f20628e-fbad-4874-840b-04021f900d15" />


```
iris.fillna(method='bfill')
```
<img width="996" height="459" alt="image" src="https://github.com/user-attachments/assets/f4912c18-f94d-466a-96ee-b6c1322f6dfb" />


```
import seaborn as sns
sns.boxplot(x='sepal_width',data=iris)
```

<img width="712" height="467" alt="image" src="https://github.com/user-attachments/assets/5fe053eb-6bc9-4e2d-92e4-31753a8d3bd0" />


```
Q1=iris.sepal_width.quantile(0.25)
Q3=iris.sepal_width.quantile(0.75)
(IQR)=Q3-Q1
print(IQR)
```
<img width="941" height="123" alt="image" src="https://github.com/user-attachments/assets/9528623f-3e1c-4603-ba22-f6da2ebc37af" />


```
ran=iris[((iris.sepal_width<(Q1-1.5*IQR))|(iris.sepal_width>(Q3+1.5*IQR)))]
ran['sepal_width']
```
<img width="859" height="237" alt="image" src="https://github.com/user-attachments/assets/f2b903df-5f13-441d-86e4-960a0d976777" />


```
sns.boxplot(x='sepal_width',data=ran)
```


<img width="826" height="459" alt="image" src="https://github.com/user-attachments/assets/d93070b2-a138-4b7c-9e5e-647b95744458" />


```
import numpy as np
import scipy.stats as stats
z=np.abs(stats.zscore(iris['petal_length']))
z
```
<img width="922" height="475" alt="image" src="https://github.com/user-attachments/assets/678e185b-106f-4984-bebe-b0082fa7314c" />



```
ir1=iris[z<3]
ir1
```
<img width="789" height="563" alt="image" src="https://github.com/user-attachments/assets/5e704b61-cef0-4560-a379-5f8ae3465300" />



# Result
         
Data Cleaning Process is verified
