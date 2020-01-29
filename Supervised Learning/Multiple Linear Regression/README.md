# :books: Multiple Linear Regression


`Multiple regression` is an extension of simple `linear regression`.

 It is used when we want to predict the value of a variable based on the value of two or more variables.
 
 `Regression` is a statistical approach to find the relationship between variables.In machine learning, it is used to predict the outcome of an event based on the relationship between variables obtained from the data-set. Regression models are used to predict a continuous value.
 
 ## :books: Building a Model

### :arrow_right: Backward Elimination

:one: Select a significance level to stay in the model (ie: SL = 0.05)

:two: Fit the full model with all possible predictors

:three: Consider the predictor with the highest P-value. If P > SL, go to step 4 otherwise go to FINISH

:four:. Remove the predictor

:five: Fit model without the predictor



### :arrow_right: Fitting Multiple Linear Regression to the Training set
```
from sklearn.linear_model import LinearRegression
regressor = LinearRegression()
regressor.fit(X_train, Y_train)
```

### :arrow_right: Predicting the Testing set result
```
Y_pred = regressor.predict(X_test)
```

### :arrow_right: Building the optimal model using Backward Elimination

`statsmodels` is a Python module that provides classes and functions for the estimation of many different statistical models, as well as for conducting statistical tests, and statistical data exploration.

Linear regression is also called Ordinary Least-Squares (OLS) 

```
import statsmodels.api as sm
X = np.append(arr = np.ones((50,1)).astype(int), values = X, axis = 1)
X_opt = np.array(X[:, [0, 1, 2, 3, 4, 5 ]], dtype = float)
regressor_OLS = sm.OLS(endog = Y, exog = X_opt).fit()
regressor_OLS.summary()
```
