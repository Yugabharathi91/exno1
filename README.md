
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



DATA  CLEANING:


<img width="1275" height="510" alt="image" src="https://github.com/user-attachments/assets/caa6ce6a-eb0f-46b3-a869-55f34f1321d2" />





<img width="626" height="423" alt="image" src="https://github.com/user-attachments/assets/4939cd80-d86f-4670-93d8-fa76cedffd97" />





<img width="846" height="355" alt="image" src="https://github.com/user-attachments/assets/c83a0a85-348a-40a3-8602-a07db2540425" />




<img width="1117" height="515" alt="image" src="https://github.com/user-attachments/assets/15464d35-95c6-471c-9013-e6db78e928f3" />





<img width="1096" height="495" alt="image" src="https://github.com/user-attachments/assets/865fa149-d5c4-4f7b-a021-b61eec749289" />





<img width="453" height="298" alt="image" src="https://github.com/user-attachments/assets/0bac7aeb-1b97-4f74-b98d-2886e7092dcd" />












<img width="1287" height="291" alt="image" src="https://github.com/user-attachments/assets/e80ecb26-4044-44e4-a4e5-512a80f091f2" />





<img width="1321" height="331" alt="image" src="https://github.com/user-attachments/assets/20949b18-646c-43bf-a085-29c36ce534cf" />












<img width="291" height="79" alt="image" src="https://github.com/user-attachments/assets/215d8ed9-a310-41e9-97d6-e929eb72209e" />






<img width="1442" height="725" alt="image" src="https://github.com/user-attachments/assets/bfa1ec91-96da-4c02-bc4e-c2ed38006f47" />






<img width="1383" height="159" alt="image" src="https://github.com/user-attachments/assets/9947fde4-0c86-42ca-ab94-b57f53c3458f" />






<img width="1389" height="161" alt="image" src="https://github.com/user-attachments/assets/9baccc2e-6ac9-4030-81ab-cce7048f0465" />






<img width="567" height="168" alt="image" src="https://github.com/user-attachments/assets/f53b3cb7-fe48-4933-98ae-c18f8e3c57c2" />






<img width="587" height="189" alt="image" src="https://github.com/user-attachments/assets/4794bb18-151e-4fcf-b3a1-067fa0ced414" />





<img width="484" height="128" alt="image" src="https://github.com/user-attachments/assets/fa7245a9-eed1-48ec-8311-aa63b079c3ca" />











<img width="555" height="263" alt="image" src="https://github.com/user-attachments/assets/9537d6b7-5c29-4da3-87e7-69213edd93c3" />






<img width="1333" height="638" alt="image" src="https://github.com/user-attachments/assets/4b922574-6bff-4827-8ca0-7103ae78ff62" />





<img width="701" height="486" alt="image" src="https://github.com/user-attachments/assets/25af92bc-a74c-4b97-8541-6356a4a12aab" />





<img width="1362" height="467" alt="image" src="https://github.com/user-attachments/assets/a5c92490-b187-4cd4-b202-36cbf0d74beb" />






<img width="1358" height="664" alt="image" src="https://github.com/user-attachments/assets/b1d7488f-b31b-44c1-9fb8-f724e21f502f" />






<img width="1293" height="466" alt="image" src="https://github.com/user-attachments/assets/44f83d6e-8056-4b45-b40e-f843ef60a588" />





<img width="1349" height="460" alt="image" src="https://github.com/user-attachments/assets/177d8385-8893-4c23-a1f4-05189012ccaf" />





<img width="1404" height="501" alt="image" src="https://github.com/user-attachments/assets/8dc5ec40-8e17-4f52-acdc-e336b0a49cc8" />







<img width="1355" height="497" alt="image" src="https://github.com/user-attachments/assets/fb8c1fa1-c7e5-4040-9deb-f558fe48e7ac" />



# Outlier Detection and Removal:
```

import pandas as pd import seaborn as sns age=[1,3,28,27,25,92,30,39,40,50,26,24,29,94] af=pd.DataFrame(age) af

```
<img width="832" height="761" alt="image" src="https://github.com/user-attachments/assets/75dc4ef7-8d97-453d-849d-bc9434b93a1e" />

```
sns.boxplot(data=af)
```


<img width="974" height="626" alt="image" src="https://github.com/user-attachments/assets/8ef2da4d-83c6-4374-bd4b-a1d13c93d8c4" />

```
import numpy as np Q1=np.percentile(age,25) Q2=np.percentile(age,50) Q3=np.percentile(age,75)
ivr=Q3-Q1 lower_bound=Q1-1.5IQR upper_bound=Q3+1.5IQR outliers=af[(af<lower_bound) | (af>upper_bound) ]
print("Quantile 1",Q1) print("Quantile 2",Q2) print("Quantile 3",Q3) print("Inter Quartile Range",IQR) print("Lower Bound",lower_bound) print("Upper Bound",upper_bound) print("Outliers",outliers)
```

<img width="1011" height="578" alt="image" src="https://github.com/user-attachments/assets/60066f7b-ada3-4fd5-8f95-809e5fcc1c4d" />

```
af=af[(af>=lower_bound) & (af<=upper_bound)] af.dropna() print("After removing outliers") af
```

<img width="573" height="525" alt="image" src="https://github.com/user-attachments/assets/94e945b0-aa60-467e-b0e0-e87c4e66ca0f" />


```
sns.boxplot(data=af)
```

<img width="543" height="413" alt="image" src="https://github.com/user-attachments/assets/d7663088-91ab-4ee4-a576-b9cb505c5aee" />

```
from scipy import stats
data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,84,87,90,93,96,99,158]
 df=pd.DataFrame(data) sns.boxplot(data=df)

```

<img width="552" height="413" alt="image" src="https://github.com/user-attachments/assets/e540f6a4-cca0-4a76-8519-26e620acdbcd" />

```
z=np.abs(stats.zscore(data)) print("Outlier values:") outliers=df[z>3] outliers
```



<img width="392" height="147" alt="image" src="https://github.com/user-attachments/assets/52755e66-5b31-4fae-88e9-07cb9a9b417f" />



```
cleaned_df=df[z<3] print("After removing outliers") cleaned_df

```


<img width="630" height="883" alt="image" src="https://github.com/user-attachments/assets/53a7885a-938a-4826-b9b8-0fa8a804ae09" />


```

sns.boxplot(data=cleaned_df)
```


<img width="1009" height="590" alt="image" src="https://github.com/user-attachments/assets/78f69280-539c-409d-a4c0-62790d4e8c60" />

```



```
 Result

         Thus the data cleaning process and outlier detection and removal on the given dataset is executed successfully.
