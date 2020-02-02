# :books: Simple Linear Regression

`Simple Linear Regression` is a technique to model a relationship betweeen a dependent variable with independent variables.

`Regression` is a statistical approach to find the relationship between variables.In machine learning, it is used to predict the outcome of an event based on the relationship between variables obtained from the data-set. Regression models are used to predict a continuous value.

## :arrow_right: Fitting simple linear regression to the Training set

```
from sklearn.linear_model import LinearRegression
regressor = LinearRegression()
regressor.fit(X_train, Y_train)
```

## :arrow_right: Predicting the Testing set results

```
Y_pred = regressor.predict(X_test)
```
