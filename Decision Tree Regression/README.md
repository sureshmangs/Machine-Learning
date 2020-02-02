# :books: Decision Tree Regression

A `decision tree` is a supervised machine learning model.

It is used to predict a target by learning decision rules from features.

It makes the decisions by breaking down a dataset into smaller and smaller datasets.

The final result is a tree with decision nodes and leaf nodes.

`Regression` is a statistical approach to find the relationship between variables.In machine learning, it is used to predict the outcome of an event based on the relationship between variables obtained from the data-set. Regression models are used to predict a continuous value.

## :arrow_right: Fitting Decision Tree Regression to the dataset

```
from sklearn.tree import DecisionTreeRegressor
regressor = DecisionTreeRegressor(random_state = 0)
regressor.fit(X, Y)
```

## :arrow_right: Predicting a new result
```
Y_pred = regressor.predict(np.array(6.5).reshape(1, -1))
Y_pred
```

## :arrow_right: Visualizing the Decision tree Regression (for higher resolution and smoother curve)
```
X_grid = np.arange(min(X), max(X), 0.01)
X_grid = X_grid.reshape((len(X_grid), 1))
plt.scatter(X, Y, color = 'red', label = 'Scatter Plot')
plt.plot(X_grid, regressor.predict(X_grid), color = 'blue', label = 'Line Plot')
plt.title('Truth or Bluff (`Truth or Bluff (Decision Tree Regression)')
plt.xlabel('Position Level')
plt.ylabel('Salary')
plt.legend()
plt.show()
```
