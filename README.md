# EXNO2DS
# AIM:
      To perform Exploratory Data Analysis on the given data set.
      
# EXPLANATION:
  The primary aim with exploratory analysis is to examine the data for distribution, outliers and anomalies to direct specific testing of your hypothesis.
  
# ALGORITHM:
STEP 1: Import the required packages to perform Data Cleansing,Removing Outliers and Exploratory Data Analysis.

STEP 2: Replace the null value using any one of the method from mode,median and mean based on the dataset available.

STEP 3: Use boxplot method to analyze the outliers of the given dataset.

STEP 4: Remove the outliers using Inter Quantile Range method.

STEP 5: Use Countplot method to analyze in a graphical method for categorical data.

STEP 6: Use displot method to represent the univariate distribution of data.

STEP 7: Use cross tabulation method to quantitatively analyze the relationship between multiple variables.

STEP 8: Use heatmap method of representation to show relationships between two variables, one plotted on each axis.

## CODING AND OUTPUT:
```
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns

df = pd.read_csv("C:/Users/admin/Documents/DS files/titanic_dataset.csv")
df
```

![image](https://github.com/user-attachments/assets/d390c47e-9824-4f3d-ad75-e30f558b71cb)

```
df.info()
```

![image](https://github.com/user-attachments/assets/29cd4a3d-f61a-4131-b4dd-faaeafa85a6c)

```
df.shape
```

![image](https://github.com/user-attachments/assets/cdcaa4ec-bc72-454c-ba74-1ce5db46feb0)

```
df.set_index("PassengerId",inplace = True)
df.describe()
```

![image](https://github.com/user-attachments/assets/31a7d3d9-fe28-4c96-a06c-388ce43327c4)

### Categorical Data Analysis:
```
df.nunique()
```

![image](https://github.com/user-attachments/assets/75975f59-31e4-4ed2-8242-27496eb023b1)

```
df["Survived"].value_counts()
```

![image](https://github.com/user-attachments/assets/98630691-e7d6-4b02-bbff-45321d869a70)

```
per=(df["Survived"].value_counts()/df.shape[0]*100).round(2)
per
```

![image](https://github.com/user-attachments/assets/e5714a29-3b4b-4193-94d0-daa4f63bc58d)

```
sns.countplot(data=df,x="Survived")
```

![image](https://github.com/user-attachments/assets/a84e95bb-a43e-4a46-a993-6aeaddfe1abf)

```
df.Pclass.unique()
```

![image](https://github.com/user-attachments/assets/413f815a-de2c-4839-bdf5-e652a4289f0a)

```
df.rename(columns = {'Sex':'Gender'},inplace = True)
df
```

![image](https://github.com/user-attachments/assets/c2389ccd-4549-470e-8459-9eddefcae11d)

### Bivariate Analysis:
```
sns.catplot(x="Gender",col="Survived",kind="count",data=df,height=5,aspect=.7)
```

![image](https://github.com/user-attachments/assets/6788947d-4d2b-48fd-9196-a1d9ece0d709)

```
sns.catplot(x="Survived",hue="Gender",data=df,kind="count")
```

![image](https://github.com/user-attachments/assets/864baa3b-fa91-482d-b635-ab56fce81189)

```
df.boxplot(column="Age",by = "Survived")
```

![image](https://github.com/user-attachments/assets/e83c7ad9-ff8c-43af-8e24-e6a26f0d33ed)

```
sns.scatterplot(x = df["Age"],y = df["Fare"])
```

![image](https://github.com/user-attachments/assets/e2efc271-5576-4568-a2fc-27ef7e6dcfc8)

```
sns.jointplot(x = "Age",y = "Fare",data=df)
```

![image](https://github.com/user-attachments/assets/a3dde832-44f9-4708-b5c2-63866e60fbde)

### Multivariate Analysis:
```
import matplotlib.pyplot as plt
import seaborn as sns

fig, ax1 = plt.subplots(figsize=(8,5))
sns.boxplot(ax=ax1, x='Pclass', y='Age', hue='Gender', data=df)

plt.show()
```

![image](https://github.com/user-attachments/assets/70e31ef0-42b8-4d01-8770-faf080dfea57)

```
 sns.catplot(data=df,col="Survived",x="Gender",hue="Pclass",kind="count")
```

![image](https://github.com/user-attachments/assets/d141f149-3c3a-4942-a284-085a1e9c4a94)

```
corr = df.corr()
sns.heatmap(corr,annot = True)
```

![image](https://github.com/user-attachments/assets/93dfd647-4c0b-4127-9fc6-9500489b220d)

```
sns.pairplot(df)
```

![image](https://github.com/user-attachments/assets/f8e99ad9-f7cb-494a-9f23-e960b2ccdcd3)



# RESULT:
         Thus, Exploratory Data Analysis has been performed on the given data set.
        
