# EXNO:4-DS
# AIM:
To read the given data and perform Feature Scaling and Feature Selection process and save the
data to a file.

# ALGORITHM:
STEP 1:Read the given Data.
STEP 2:Clean the Data Set using Data Cleaning Process.
STEP 3:Apply Feature Scaling for the feature in the data set.
STEP 4:Apply Feature Selection for the feature in the data set.
STEP 5:Save the data to the file.

# FEATURE SCALING:
1. Standard Scaler: It is also called Z-score normalization. It calculates the z-score of each value and replaces the value with the calculated Z-score. The features are then rescaled with x̄ =0 and σ=1
2. MinMaxScaler: It is also referred to as Normalization. The features are scaled between 0 and 1. Here, the mean value remains same as in Standardization, that is,0.
3. Maximum absolute scaling: Maximum absolute scaling scales the data to its maximum value; that is,it divides every observation by the maximum value of the variable.The result of the preceding transformation is a distribution in which the values vary approximately within the range of -1 to 1.
4. RobustScaler: RobustScaler transforms the feature vector by subtracting the median and then dividing by the interquartile range (75% value — 25% value).

# FEATURE SELECTION:
Feature selection is to find the best set of features that allows one to build useful models. Selecting the best features helps the model to perform well.
The feature selection techniques used are:
1.Filter Method
2.Wrapper Method
3.Embedded Method

# CODING AND OUTPUT

```
import numpy as np
import pandas as pd
from scipy import stats 
df=pd.read_csv("/content/bmi.csv")
df
```
<img width="749" height="512" alt="image" src="https://github.com/user-attachments/assets/6dc39432-f42d-4370-b27d-bebe10c3d401" />

```
df.isna()
```
<img width="779" height="516" alt="image" src="https://github.com/user-attachments/assets/64602436-243f-4972-bccb-aa067797690c" />

```
df.head()
```
<img width="743" height="250" alt="image" src="https://github.com/user-attachments/assets/ea37ee26-8fc7-4a79-a28a-b05881615d6b" />

```
from sklearn.preprocessing import StandardScaler
scaler=StandardScaler()
df[["Height","Weight"]]=scaler.fit_transform(df[["Height","Weight"]])
df
```
<img width="749" height="511" alt="image" src="https://github.com/user-attachments/assets/64d5e72c-1b43-4cdd-a9ef-20dd2cb3fe23" />

```
from sklearn.preprocessing import MinMaxScaler
scaler=MinMaxScaler()
df[["Height","Weight"]]=scaler.fit_transform(df[["Height","Weight"]])
df
```
<img width="764" height="514" alt="image" src="https://github.com/user-attachments/assets/031dd95a-df7d-4cef-a627-0b041d2f3523" />

```
from sklearn.preprocessing import Normalizer
scaler=Normalizer()
df[["Height","Weight"]]=scaler.fit_transform(df[["Height","Weight"]])
df
```
<img width="782" height="506" alt="image" src="https://github.com/user-attachments/assets/baec59b0-cb17-4b48-a630-aa86c6d232b8" />

```
from sklearn.preprocessing import MaxAbsScaler
scaler=MaxAbsScaler()
df[["Height","Weight"]]=scaler.fit_transform(df[["Height","Weight"]])
df
```
<img width="745" height="510" alt="image" src="https://github.com/user-attachments/assets/3149db1c-489d-43e8-aaae-dc8f24894000" />

```
from sklearn.preprocessing import RobustScaler
scaler=RobustScaler()
df[["Height","Weight"]]=scaler.fit_transform(df[["Height","Weight"]])
df
```
<img width="742" height="503" alt="image" src="https://github.com/user-attachments/assets/6a6d2d99-e583-4699-889b-9f22aa45b95a" />

```
import pandas as pd
import numpy as np
from scipy import stats
df=pd.read_csv("/content/income(1) (1).csv")
df
```
<img width="783" height="772" alt="image" src="https://github.com/user-attachments/assets/51db49f3-2203-4558-8db2-d6b4bb3e0f1a" />

```
df.columns
```
<img width="748" height="97" alt="image" src="https://github.com/user-attachments/assets/1a9fdad7-66f9-4316-9d5e-528f3ee37651" />

```
df.dropna()
```
<img width="777" height="681" alt="image" src="https://github.com/user-attachments/assets/ec7dcc95-425c-4d2f-93c4-780af0cdc918" />

```
df.isnull().sum()
```
<img width="748" height="599" alt="image" src="https://github.com/user-attachments/assets/0886a87f-1cfa-43ca-b849-23ea70ab04e3" />

```
import pandas as pd
import numpy as np
from scipy.stats import chi2_contingency
import seaborn as sns
tips=sns.load_dataset('tips')
tips.head()
```
<img width="722" height="254" alt="image" src="https://github.com/user-attachments/assets/e8987d72-6c0a-46e0-979b-8aa4a40c1375" />

```
tips.time.unique()
```
<img width="738" height="60" alt="image" src="https://github.com/user-attachments/assets/d6304255-21cc-4a06-8288-a255aee5ef50" />

```
contingency_table=pd.crosstab(tips['sex'],tips['time'])
print(contingency_table)
```
<img width="429" height="106" alt="image" src="https://github.com/user-attachments/assets/ba67d02a-7215-49a6-b2d0-60a51306450c" />

```
chi2,p,_,_=chi2_contingency(contingency_table)
print(f"Chi-Square Statistics: {chi2}")
print(f"P-Value: {p}")
```
<img width="794" height="52" alt="image" src="https://github.com/user-attachments/assets/d17de0df-3432-4cbd-87b2-a92d6c075a0a" />

# RESULT:
The result is executed successfully.
