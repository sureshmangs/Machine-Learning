# :books: Random Forest Regression

A `decision tree` is a supervised machine learning model.

It is used to predict a target by learning decision rules from features.

It makes the decisions by breaking down a dataset into smaller and smaller datasets.

The final result is a tree with decision nodes and leaf nodes.

`Random forest` is a Supervised Learning algorithm which uses `ensemble learning method` for classification and regression.

`Ensemble method` is a technique that combines the predictions from multiple machine learning algorithms together to make more accurate predictions than any individual model.

## :arrow_right: Random Forest Intuition

:one: Pick at random K data points from the training set.

:two: Build the Decision Tree associated to these K data points.

:three: Choose the number Ntree of treesyou want to build and repeat step 1 and step 2.

:four: For a new data point, make each one of your Ntree predict the value of Y to for the data point in question, and assign the new data point the average across all of the predicted Y values.




## :arrow_right: Fitting Random Forest Regression to the dataset

```
from sklearn.ensemble import RandomForestRegressor
regressor = RandomForestRegressor(n_estimators = 300, random_state = 0)
regressor.fit(X, Y)
```

## :arrow_right: Predicting a new result
```
Y_pred = regressor.predict(np.array(6.5).reshape(1, -1))
Y_pred
```

## :arrow_right: Visualizing the Random Forest Regression (for higher resolution and smoother curve)
```
X_grid = np.arange(min(X), max(X), 0.01)
X_grid = X_grid.reshape((len(X_grid), 1))
plt.scatter(X, Y, color = 'red', label = 'Scatter Plot')
plt.plot(X_grid, regressor.predict(X_grid), color = 'blue', label = 'Line Plot')
plt.title('Truth or Bluff (`Truth or Bluff (Random Forest Regression)')
plt.xlabel('Position Level')
plt.ylabel('Salary')
plt.legend()
plt.show()
```
