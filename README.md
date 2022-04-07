Ex-02_DS_Outlier:


AIM:

To detect and remove outliers from the given data and save the final data.

EXPLANATION:

Outlier is a data object that deviates significantly from the rest of the data objects and behaves in a different manner. They can be caused by measurement or execution errors. The analysis of outlier data is referred to as outlier analysis or outlier mining. The box plot is a useful graphical display for describing the behavior of the data in the middle as well as at the ends of the distributions. The box plot uses the median and the lower and upper quartiles (defined as the 25th and 75th percentiles). If the lower quartile is Q1 and the upper quartile is Q3, then the difference (Q3 - Q1) is called the interquartile range or IQ.

ALGORITHM:

STEP 1:

Import the packages pandas and numpy.

STEP 2:

Read the csv file and convert it into Dataframe format.

STEP 3:

Use drop function to remove a "Gender" coloumn from the Dataframe.

STEP 4:

Apply Graphical Method "Box plot" which exhibits the Outliers.

STEP 5:

Apply Z-score function to detect the outliers.

STEP 6:

Apply Statistical Method "Interquartile Range(IQR)" to remove the Outliers from the Dataset.

STEP 7:

Finally save the updated data set and display the data.

CODE:

```
import pandas as pd
df=pd.read_csv("weight.csv")
df
print("Removing non numeric values from the data and it's graph plot is:")
df=df.drop("Gender",axis=1)
df
df.boxplot()
df

import numpy as np
from scipy import stats
z=np.abs(stats.zscore(df))
print("Z scores and data set after removing outliers from Weight using z scores and data manuplation is:")
print(z)
df1=df.copy()
df1=df1[(z<3).all(axis=1)]
df1

print("Graph for the updated Data set:")
df1.boxplot()

df2=df.copy()
print("After removing outliers from Height the updated data set using IQR and its graph plot is:")
q1=df2.quantile(0.25)
q3=df2.quantile(0.75)
IQR=q3-q1
df_new=df2[((df2>a1-1.5*IQR)&(df2<=q3+1.5*IQR)).all(axis=1)]
df_new
df_new.boxplot()
df_new

print("Finalized Data set is:")
df_new
```

# OUTPUT :  

![OUTPUT](/IMAGE/I.png)
![OUTPUT](/IMAGE/I1.png)
![OUTPUT](/IMAGE/I2.png)
![OUTPUT](/IMAGE/I3.png)
![OUTPUT](/IMAGE/I4.png)
![OUTPUT](/IMAGE/I5.png)
![OUTPUT](/IMAGE/I6.png)
![OUTPUT](/IMAGE/I7.png)
![OUTPUT](/IMAGE/I9.png)

#  RESULT :
The Outliers are detected by using pandas and numpy and removed from the Dataset successfully.
