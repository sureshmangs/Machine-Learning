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

## :books: Encoding categorical data

LabelEncoder is a way to encode class levels.

Encode target labels with value between 0 and n_classes-1.

It is used to convert categorical data, or text data, into numbers,

```
from sklearn.preprocessing import LabelEncoder
labelencoder_X = LabelEncoder()
X[:, 0] = labelencoder_X.fit_transform(X[:, 0])     # first column
```

After implementing the label encoding, our model might think that a column has data with some kind of order or hierarchy, even when we don't have it. To overcome this ‘OneHotEncode’ is used.

OneHotEncode represents the categorical variables as binary vectors.

```
from sklearn.preprocessing import OneHotEncoder
from sklearn.compose import ColumnTransformer

ct = ColumnTransformer(
    [('one_hot_encoder', OneHotEncoder(), [0])],     # first column
    remainder='passthrough'                     
)

X = np.array(ct.fit_transform(X), dtype=np.float)
```

Or you can use the OneHotEncoder directly
```
from sklearn.preprocessing import OneHotEncoder
transformer = ColumnTransformer(
    transformers=[
        ("OneHotEncoder",        # Just a name
         OneHotEncoder(), # The transformer class
         [3]              # The column(s) to be applied on.
         )
    ],
    remainder='passthrough' # donot apply anything to the remaining columns
)
X = transformer.fit_transform(X.tolist())
```

## :books: Splitting dataset into training set and testing set

Used for splitting the dataset into the training set and the testing set.

 train_test_split divide the datasets into two parts for testing and training .

```
from sklearn.model_selection import train_test_split
X_train, X_test, Y_train, Y_test = train_test_split(X, Y, test_size = 0.2, random_state = 0)
```


## :books: Feature scaling

Feature Scaling is a technique used at the time of Data Pre Processing to normalise the independent variables or features of data in a particular range.

Standardisation:

```
x_stand = ( x - mean(x) ) / ( standard devation(x) )
```

Normalisation:

```
x_norm = ( x - min(x) ) / ( max(x) - min(x) )
```

StandardScaler normalises data features in such a way that it has mean as 0 and standard deviation as 1.

```
from sklearn.preprocessing import StandardScaler
sc_X = StandardScaler()
X_train = sc_X.fit_transform(X_train)
X_test = sc_X.transform(X_test)
```

## :books: Visualizing results

A scatter plot of y vs x 

Plot y versus x as lines or markers

```
plt.scatter(X, Y, color = 'red', label = 'Scatter Plot')
plt.plot(X, Y, color = 'blue', label = 'Line Plot')
plt.title('Title of the Plot')
plt.xlabel('Xlabel plot')
plt.ylabel('Ylabel plot')
plt.legend()
plt.show()
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



