# Ex:05 Feature Generation

# AIM:
To read the given data and perform Feature Generation process and save the data to a file.

# Explanation:
Feature Generation (also known as feature construction, feature extraction or feature engineering) is the process of transforming features into new features that better relate to the target.

# ALGORITHM:
STEP 1
Read the given Data

STEP 2
Clean the Data Set using Data Cleaning Process

STEP 3
Apply Feature Generation techniques to all the feature of the data set

STEP 4
Save the data to the file

# PROGRAM:

# FEATURE ENCODING
```
import pandas as pd
df=pd.read_csv("/content/Encoding Data.csv")
df
from sklearn.preprocessing import LabelEncoder,OrdinalEncoder
pm=['Hot','Warm','Cold']
e1=OrdinalEncoder(categories=[pm])
e1.fit_transform(df[["ord_2"]])
df['bo2']=e1.fit_transform(df[["ord_2"]])
df
le=LabelEncoder()
dfc=df.copy()
dfc['ord_2']=le.fit_transform(dfc['ord_2'])
dfc
from sklearn.preprocessing import OneHotEncoder
ohe=OneHotEncoder(sparse=False)
df2=df.copy()
enc=pd.DataFrame(ohe.fit_transform(df2[['nom_0']]))
df2=pd.concat([df2,enc],axis=1)
df2
pd.get_dummies(df2,columns=["nom_0"])
pip install --upgrade category_encoders
from category_encoders import BinaryEncoder
df=pd.read_csv("/content/data.csv")
df
be=BinaryEncoder()
nd=be.fit_transform(df['Ord_1'])
dfb=pd.concat([df,nd],axis=1)
dfb1=df.copy()
dfb
from category_encoders import TargetEncoder
te=TargetEncoder()
cc=df.copy()
new=te.fit_transform(X=cc["City"],y=cc["Target"])
cc=pd.concat([cc,new],axis=1)
cc
```

# FEATURE SCALING:

```
import pandas as pd
from scipy import stats
import numpy as np
df=pd.read_csv("/content/bmi.csv")
df.head()
df.dropna()
max_vals=np.max(np.abs(df[['Height','Weight']]))
max_vals
from sklearn.preprocessing import StandardScaler
sc=StandardScaler()
df1=df.copy()
df1[['Height','Weight']]=sc.fit_transform(df1[['Height','Weight']])
df1.head(10)
max_vals=np.max(np.abs(df1[['Height','Weight']]))
max_vals
min_vals=np.min(np.abs(df1[['Height','Weight']]))
min_vals
from sklearn.preprocessing import MinMaxScaler
scaler=MinMaxScaler()
df2=df.copy()
df2[['Height','Weight']]=sc.fit_transform(df2[['Height','Weight']])
df2.head(10)
df2.head()
from sklearn.preprocessing import Normalizer
sc=Normalizer()
df3=df.copy()
df3[['Height','Weight']]=sc.fit_transform(df3[['Height','Weight']])
df3
df3.head(10)
from sklearn.preprocessing import MaxAbsScaler
sc=MaxAbsScaler()
df4=df.copy()
df4[['Height','Weight']]=sc.fit_transform(df4[['Height','Weight']])
df4
from sklearn.preprocessing import RobustScaler
sc=RobustScaler()
df5=df.copy()
df5[['Height','Weight']]=sc.fit_transform(df5[['Height','Weight']])
df5
df5.head()
```

# OUTPUT:

# FEATURE ENCODING

<img width="415" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/4a40c4ec-b7ca-4c04-9039-9629c049ba58">


<img width="430" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/c31a5fb5-26a7-4c9d-90c2-c953c434ab55">


<img width="445" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/54c26f18-3277-4b20-8ead-8da78675b39d">


<img width="500" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/07643e63-25b7-4949-ae9f-24197684645a">


<img width="600" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/10e3a613-fd4a-463d-9c47-373875cb904b">


<img width="613" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/e0729f64-0197-477f-86cb-2f820ae403fe">


<img width="629" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/4923f6d7-2e7e-494b-af08-5e2a503c667b">


<img width="635" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/9bd8ceab-7aa5-42e3-914f-7619878324b2">


<img width="645" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/25c70cc2-5db9-4da7-afcd-e1b80e81f8ae">


<img width="665" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/bed8f82c-f569-4b7c-800a-b1ebd6559859">


<img width="685" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/a6d98f04-383b-45b3-8b1d-e1190973bb3e">


# FEATURE SCALING:

<img width="400" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/9624cb42-7363-4a6c-b52c-7dfdd2ec3d8e">


<img width="415" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/4bef8b46-9f98-40b1-b609-04d032c6039b">


<img width="985" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/b9f259ec-5c31-4ddf-aa82-dfe7dcbf7896">


<img width="445" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/2e8ea8aa-4735-4f7c-8a2d-6e6a71fdae59">


<img width="995" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/1ef92584-3458-4d5f-880a-6e036ef7a1ac">


<img width="485" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/c4f6836d-fcf8-47a5-b1bc-69f8e0f5dd60">


<img width="496" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/755df794-db13-4a4e-835b-fe883a5571eb">


<img width="510" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/8287a836-776d-479f-8355-e95d4a74b858">


<img width="530" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/08048583-37c0-4c1c-b35c-fa400465810e">


<img width="545" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/b9773e82-1e99-40da-ae2e-f33b4cdec09a">


<img width="564" alt="image" src="https://github.com/Vineesha29031970/ODD2023-Datascience-Ex-05/assets/133136880/5cd19d5e-81e8-4c58-9991-8f2413b2357a">


# RESULT:
Thus the Feature Generation and Feature Scaling process is applied to the given data set.
