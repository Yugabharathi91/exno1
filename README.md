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
# Reading the file:
```
import pandas as pd
df=pd.read_csv("SAMPLEIDS.csv")
df
```
# Output
<img width="1013" height="818" alt="Screenshot 2025-08-27 201057" src="https://github.com/user-attachments/assets/1fc755b0-9cf1-454f-8bca-179c44a4e168" />

# Head Command:
```
df.head()
```

# Output
<img width="1012" height="255" alt="Screenshot 2025-08-27 201220" src="https://github.com/user-attachments/assets/a346b52d-c529-41e2-82db-388680ad28ac" />

# Tail Command:
```
df.tail()
```

# Output
<img width="1053" height="245" alt="Screenshot 2025-08-27 201329" src="https://github.com/user-attachments/assets/06b82b27-7ee1-4a15-b267-ba7652e018c9" />

# IsNull Command:
```
df.isnull()
```

# Output
<img width="819" height="847" alt="Screenshot 2025-08-27 201509" src="https://github.com/user-attachments/assets/8b07b5c2-caaa-4fc8-a962-8cd5c013ec4a" />

# Sum Command:
```
df.isnull().sum()
```

# Output
<img width="164" height="571" alt="Screenshot 2025-08-27 201718" src="https://github.com/user-attachments/assets/b5185c5a-f7c0-46c3-9d76-7fdb5532604e" />

# Any Command:
```
df.isnull().any()
```

# Output
<img width="194" height="571" alt="image" src="https://github.com/user-attachments/assets/45b6b57f-31d1-492c-80b1-a4037546e11e" />

# Drop-Row Command:
```
df.dropna(axis=0)
```

# Output
<img width="1054" height="559" alt="image" src="https://github.com/user-attachments/assets/b1a22af4-c3ed-41d9-a605-982e1f238304" />

# Fill Command:
```
df.fillna(2)
```

# Output
<img width="1019" height="855" alt="image" src="https://github.com/user-attachments/assets/7c68897c-0d7d-4168-a5d0-62f0273b387d" />

# Forward Fill Command:
```
df.fillna(method='ffill')
```

# Output
<img width="1012" height="856" alt="image" src="https://github.com/user-attachments/assets/18789853-cb5b-4b8f-a547-c42d3f89bd3c" />

# Backward Fill Command:
```
df.fillna(method='bfill')
```

# Output
<img width="1011" height="855" alt="image" src="https://github.com/user-attachments/assets/a096446b-09b4-4236-93bd-0c47ca39f56b" />

# Read iris.csv data:
```
ir=pd.read_csv("iris.csv")
ir
```

# Output
<img width="677" height="515" alt="image" src="https://github.com/user-attachments/assets/367d26cd-274b-490b-abd9-ae8b431654b1" />

# Describe Command:
```
ir.describe()
```

# Output
<img width="615" height="367" alt="image" src="https://github.com/user-attachments/assets/c087ed60-7187-4766-87a6-b4871949e92e" />

# Box Plot Method:
```
import seaborn as sns
sns.boxplot(x='sepal_width',data=ir)
```

# Output
<img width="707" height="579" alt="image" src="https://github.com/user-attachments/assets/9468e6b2-b675-4cd4-9059-812f38978e9d" />

# IQR Method:
```
q1=ir.sepal_width.quantile(0.25)
q3=ir.sepal_width.quantile(0.75)
iqr=q3-q1
print(iqr)
```

# Output
<img width="65" height="43" alt="image" src="https://github.com/user-attachments/assets/294e3793-ace0-4717-848c-70c9e1f99200" />

# Finding the Lower and Upper bound:
```
bound=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
bound['sepal_width']
```

# Output
<img width="196" height="260" alt="image" src="https://github.com/user-attachments/assets/fc4b233b-969d-4a0b-90ca-7997fc4cbbcf" />

# Removing Outliers:
```
debound=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))]
debound
```

# Output
<img width="688" height="516" alt="image" src="https://github.com/user-attachments/assets/d103fcaa-3e78-4bad-837d-44fd9ef85def" />

# Box Plot:
```
sns.boxplot(x='sepal_width',data=debound)
```

# Output
<img width="700" height="574" alt="image" src="https://github.com/user-attachments/assets/a92a4aa7-40dc-4395-96b4-e56d50309d8a" />

# Z-Score Method:
```
import scipy.stats as stats
import numpy as np
z=np.abs(stats.zscore(ir['sepal_width']))
z
```

# Output
<img width="715" height="667" alt="image" src="https://github.com/user-attachments/assets/f15410a5-9e74-4d7d-8e22-ddf4e4c11fe3" />

# Removing Outliers
```
ir1=ir[z<3]
ir1
```

# Output
<img width="665" height="519" alt="image" src="https://github.com/user-attachments/assets/bedf21e5-26a6-468c-bf93-dd61e1fb2856" />

# Result
Thus, we have read the given data and performed data cleaning and saved the cleaned data to a file successfully.
