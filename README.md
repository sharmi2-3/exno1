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
data=pd.read_csv("sampleids.csv")
data

```
<img width="519" height="462" alt="image" src="https://github.com/user-attachments/assets/5ea040cd-af30-4c38-93e1-74c653c6aa37" />

```
data.info()
```
<img width="348" height="317" alt="image" src="https://github.com/user-attachments/assets/92ced5fe-ccca-4fdd-ac4f-fb2c61ccf6d9" />

```
data.head()
```
<img width="532" height="123" alt="image" src="https://github.com/user-attachments/assets/590bc3b1-5d50-46fd-9985-9e435873dc7a" />

```
data.tail()
```
<img width="527" height="127" alt="image" src="https://github.com/user-attachments/assets/24fa3241-be96-441c-aea7-870aa1b6b853" />

```
data.describe()
```
<img width="469" height="196" alt="image" src="https://github.com/user-attachments/assets/b8d06bb8-e988-43f9-aa85-7cfe60a7177b" />

```
data.isnull()

```

<img width="267" height="240" alt="image" src="https://github.com/user-attachments/assets/5e2ca808-7217-4cb3-bb8f-eaa602ad9568" />

```
data.isnull().sum()

```

<img width="116" height="160" alt="image" src="https://github.com/user-attachments/assets/94f03061-c9dd-4a7a-8e19-70a8221ec2d9" />

```
data.dropna()
```

<img width="527" height="304" alt="image" src="https://github.com/user-attachments/assets/bc0a61fd-1d6e-46e8-a629-230d548fbf68" />

```
data1.fillna(method='ffill')
```

<img width="543" height="423" alt="image" src="https://github.com/user-attachments/assets/b262bb01-a28f-4e8e-8d48-f30ebdd3256b" />

```
df.fillna(method='bfill')

```

<img width="538" height="415" alt="image" src="https://github.com/user-attachments/assets/dada92fa-50fc-4038-b1f8-e0e061fe6d94" />

```
df.fillna({'NAME':'RIYA','GENDER':'FEMALE','ADDRESS':'CHENNAI','M1':90,'M2':90,'M3':89,'M4':87})
```


<img width="517" height="384" alt="image" src="https://github.com/user-attachments/assets/8f471eef-244a-41fe-b822-f48b0725421f" />


```
import numpy as np
from scipy import stats
ir=pd.read_csv("iris.csv")
ir
```

<img width="502" height="394" alt="image" src="https://github.com/user-attachments/assets/0086cd53-2506-44d0-a0f6-ccce349f4fe9" />

```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)

```

<img width="551" height="459" alt="image" src="https://github.com/user-attachments/assets/ed123d39-9c83-4fec-8a7f-270aa4376794" />

```
q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr)
```

<img width="75" height="34" alt="image" src="https://github.com/user-attachments/assets/4e9f7ab9-6cc6-4e2c-9c1c-dc9892dd9b22" />

```
delid=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
delid
```

<img width="525" height="397" alt="image" src="https://github.com/user-attachments/assets/0af7df7d-83bb-417d-b735-4be5c6b68c3a" />
```
z=np.abs(stats.zscore(ir['sepal_width']))
z
```

<img width="439" height="258" alt="image" src="https://github.com/user-attachments/assets/c8ec2aaf-47ec-4ca0-b5fd-e700a362851e" />

```
ir1=ir[z<3]
ir1
```

<img width="516" height="389" alt="image" src="https://github.com/user-attachments/assets/e51c5b38-8b6a-40a4-9c90-696689894c87" />


# Result
Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
          <<include your Result here>>
