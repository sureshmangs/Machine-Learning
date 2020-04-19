# :books: Random Forest Classification

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




## :arrow_right: Fitting Random Forest Classification to the dataset

```
from sklearn.ensemble import RandomForestClassifier
classifier = RandomForestClassifier(n_estimators = 10, criterion = 'entropy', random_state = 0)
classifier.fit(X_train, Y_train)
```

## :arrow_right: Predicting a new result
```
Y_pred = classifier.predict(X_test)
Y_pred
```

## :arrow_right: Visualizing the Random Forest Classification
```
from matplotlib.colors import ListedColormap
X_set, y_set = X_train, Y_train
X1, X2 = np.meshgrid(np.arange(start = X_set[:, 0].min() - 1, stop = X_set[:, 0].max() + 1, step = 0.01),
                     np.arange(start = X_set[:, 1].min() - 1, stop = X_set[:, 1].max() + 1, step = 0.01))
plt.contourf(X1, X2, classifier.predict(np.array([X1.ravel(), X2.ravel()]).T).reshape(X1.shape),
             alpha = 0.75, cmap = ListedColormap(('red', 'green')))
plt.xlim(X1.min(), X1.max())
plt.ylim(X2.min(), X2.max())
for i, j in enumerate(np.unique(y_set)):
    plt.scatter(X_set[y_set == j, 0], X_set[y_set == j, 1],
                c = ListedColormap(('red', 'green'))(i), label = j)
plt.title('Random Forest Classification')
plt.xlabel('Age')
plt.ylabel('Estimated Salary')
plt.legend()
plt.show()
```
