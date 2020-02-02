# :books: Support Vector Regression

A `support vector machine` constructs a hyperplane or set of hyperplanes in a high- or infinite-dimensional space, which can be used for classification, regression.


`Regression` is a statistical approach to find the relationship between variables.In machine learning, it is used to predict the outcome of an event based on the relationship between variables obtained from the data-set. Regression models are used to predict a continuous value.



### :arrow_right: Fitting SVR to the data set

```
from sklearn.svm import SVR
regressor = SVR(kernel = 'rbf', gamma = 'auto')
Y = Y.ravel()
regressor.fit(X, Y)
```

### :arrow_right: Predicting a new result

```
Y_pred = sc_Y.inverse_transform(regressor.predict(sc_X.transform(np.array(6.5).reshape(1,-1))))
Y_pred
```

### :arrow_right: Visualizing the SVR Regression results

```
plt.scatter(X, Y, color = 'red', label = 'Scatter Plot')
plt.plot(X, regressor.predict(X), color = 'blue', label = 'Line Plot')
plt.title('Truth or Bluff (SVR Regression)')
plt.xlabel('Position Level')
plt.ylabel('Salary')
plt.legend()
plt.show()
```


