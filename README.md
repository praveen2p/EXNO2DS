# Ex.no:2 - EDA Analysis using Python.

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

## CODING AND OUTPUT
```

import pandas as pd
import numpy as np
df=pd.read_csv("/content/titanic_dataset.csv")
df
```


## Output:
<img width="1540" height="657" alt="image" src="https://github.com/user-attachments/assets/30e8712b-0744-4bd6-ad8f-57e7cf5fdef9" />


```

import matplotlib.pyplot as plt
import seaborn as sns

 df.info()
```

## Output:
<img width="597" height="470" alt="image" src="https://github.com/user-attachments/assets/7a341aa6-1427-48cc-9cf0-6299b9b4a75e" />



```

df.describe()
```

## Output:
<img width="1014" height="435" alt="image" src="https://github.com/user-attachments/assets/c3c40441-704e-405a-8816-2d7a8f29f314" />


```
df.dtypes

```

## Output:
<img width="593" height="620" alt="image" src="https://github.com/user-attachments/assets/f2c97711-6c65-4352-ab8b-2607c9b474a6" />


```
df['Age'].value_counts()
```

## Output:
<img width="608" height="658" alt="image" src="https://github.com/user-attachments/assets/c876580d-be21-4d0b-b83b-1fcfd0bf4d0d" />


```
df.set_index("PassengerId",inplace=True)
df.describe()
```

## Output:
<img width="958" height="443" alt="image" src="https://github.com/user-attachments/assets/4aea8742-ec39-4108-b14b-7583f69f9c62" />


```
df.nunique()

```

## Output:
<img width="869" height="580" alt="image" src="https://github.com/user-attachments/assets/0d1e9aa1-14b0-432d-8226-c2ab831fcc46" />


```
sns.countplot(x="Age",data=df)

```

## Output:

<img width="936" height="633" alt="image" src="https://github.com/user-attachments/assets/12c38c27-c222-427d-80ca-7ec67db4b443" />


```
df.Pclass.unique()
```

## Output:
<img width="434" height="94" alt="image" src="https://github.com/user-attachments/assets/64254798-5687-48c8-be95-15152f68aebd" />


```
df.rename(columns={"Sex":"Gender"},inplace=True)
df

```

## Output:
<img width="1488" height="618" alt="image" src="https://github.com/user-attachments/assets/e7a4bb9d-bd6f-43ca-9652-32bf6ba165a0" />


# Bivariate analysis
```
sns.catplot(x='Gender',col='Survived',kind='count',data=df,height=5,aspect=0.7)
```

## Output:
<img width="1184" height="689" alt="image" src="https://github.com/user-attachments/assets/bc5e38d3-c67f-472d-84b1-009ee2fef628" />


```
df.boxplot(column="Age",by="Survived")

```

## Output:
<img width="947" height="643" alt="image" src="https://github.com/user-attachments/assets/9ada04f5-cc56-4253-b708-26052b036607" />


```
sns.scatterplot(x="Age",y="Fare",data=df)
```

## Output:
<img width="970" height="626" alt="image" src="https://github.com/user-attachments/assets/438e9ca8-6adc-46cb-bf1a-931e071e482e" />


```

plt=sns.boxplot(x="Pclass",y="Age",hue='Gender',data=df)
```

## Output:
<img width="926" height="614" alt="image" src="https://github.com/user-attachments/assets/30d5d119-3ef7-406c-b6e9-9167e9f38bc7" />



```
import seaborn as sns

sns.catplot(x="Pclass", y="Age", hue="Gender", col="Survived",
            kind="box", data=df)


```

## Output:
<img width="1478" height="695" alt="image" src="https://github.com/user-attachments/assets/1846d5c6-c819-4462-a574-c5dcc213d6be" />



```
sns.catplot(x="Gender", hue="Pclass", col="Survived",kind="count", data=df)

```

## Output:
<img width="1407" height="675" alt="image" src="https://github.com/user-attachments/assets/e1461a46-75e6-4154-8a24-7348fd2af357" />




```
numeric_df = df.select_dtypes(include=['number'])
corr = numeric_df.corr()
sns.heatmap(corr,annot=True)

```

## Output:

<img width="882" height="657" alt="image" src="https://github.com/user-attachments/assets/8ad4a974-fd23-4fe2-be59-02d4e5745ea9" />



```
numeric_df = df.select_dtypes(include=['number'])
corr = numeric_df.corr()
sns.heatmap(corr)
```

## Output:
<img width="792" height="644" alt="image" src="https://github.com/user-attachments/assets/1e924db4-aaaf-4d68-9435-f691be4ac120" />



# RESULT:
thus the Program was executed and verified successfully.
        
