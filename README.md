# Ex-02_DS_Outlier
import pandas as pd
df = pd.read_csv("weight.csv")
df
df.drop('Gender',axis=1)
df
df.drop('Gender',axis=1,inplace=True)
df
df.boxplot()
from scipy import stats
import numpy as np
z = np.abs(stats.zscore(df))
z
df1 = df.copy()
df1 = df[(z<3).all(axis = 1)]
df1.boxplot()
df1
df2 = df.copy()
q1 = df2.quantile(0.25)
q3 = df2.quantile(0.75)
IQR = q3-q1
df2_new=df2[((df2>=q1-1.5*IQR)&(df2<=q3+1.5*IQR)).all(axis=1)]
df2_new.boxplot()
df2_new![Screenshot (116)](https://user-images.githubusercontent.com/79370364/161583964-19cf6f55-2b9b-4748-b75d-6e5b25afeae6.png)
![Screenshot (117)](https://user-images.githubusercontent.com/79370364/161583970-57399120-6b1b-4096-943e-17937276df65.png)
![Screenshot (118)](https://user-images.githubusercontent.com/79370364/161583973-d89af04c-2bfd-4cb7-a1ac-eba6a3ece294.png)
![Screenshot (119)](https://user-images.githubusercontent.com/79370364/161583977-610086e0-49fd-464d-ad4d-645840792d72.png)
![Screenshot (120)](https://user-images.githubusercontent.com/79370364/161583981-33305104-ef67-400d-8b56-4a0543b6e835.png)
![Screenshot (121)](https://user-images.githubusercontent.com/79370364/161583989-fedef37b-8420-4382-a070-af3443bc5a96.png)
