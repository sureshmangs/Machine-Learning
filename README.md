# :rocket: Machine Learning

:pencil2: Implementing Machine Learning Algorithms


## :books: Libraries

### :arrow_right: NumPy

`Numpy` (short for Numerical Python) is a library used for computing scientific/mathematical data.

It gives the ability to create multidimensional array objects and perform faster mathematical operations.

#### Usage
`import numpy as np`

### :arrow_right: Matplotlib

`Matplotlib` is a library of python.

Using `Matplotlib` you can plot graphs, histogram, bar plot and other sort of things.

It is the Python's equivalent of MATLAB

`matplotlib.pyplot` is a collection of command style functions that make `matplotlib` work like MATLAB.

#### Usage
`import matplotlib.pyplot as plt`

### :arrow_right: Pandas

`Pandas` (Python Data Analysis Library) is a library for data manipulation and analysis.

The `Pandas` module is used for working with tabular data

#### Usage
`import pandas as pd`

## :books: Taking care of missing values

SimpleImputer class provides basic strategies for imputing missing values.


```
import numpy as np
from sklearn.impute import SimpleImputer 
imputer = SimpleImputer(missing_values=np.nan,strategy='mean')
imputer = imputer.fit(X[:, :])
X[:, :] = imputer.transform(X[:, :])
```

## :books: Python Quickstart

### :arrow_right: iloc

iloc indexer for Pandas Dataframe is used for integer-location based indexing / selection by position.


```
# Single selections using iloc and DataFrame
# Rows:
data.iloc[0] # first row of data frame
data.iloc[1] # second row of data frame
data.iloc[-1] # last row of data frame
# Columns:
data.iloc[:,0] # first column of data frame
data.iloc[:,1] # second column of data frame
data.iloc[:,-1] # last column of data frame
```
```

# Multiple row and column selections using iloc and DataFrame
data.iloc[0:5] # first five rows of dataframe
data.iloc[:, 0:2] # first two columns of data frame with all rows
data.iloc[[0,3,6,24], [0,5,6]] # 1st, 4th, 7th, 25th row + 1st 6th 7th columns
data.iloc[0:5, 5:8] # first 5 rows and 5th, 6th, 7th columns of data frame
```



