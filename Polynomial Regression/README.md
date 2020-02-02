# :books: Polynomial Regression

`Polynomial Regression` is a form of `linear regression` in which the relationship between the independent variable x and dependent variable y is modeled as an nth degree polynomial.

`Regression` is a statistical approach to find the relationship between variables.In machine learning, it is used to predict the outcome of an event based on the relationship between variables obtained from the data-set. Regression models are used to predict a continuous value.

## :arrow_right: Fitting polynomial regression to the Training set

```
from sklearn.preprocessing import PolynomialFeatures
poly_reg = PolynomialFeatures(degree = 4)
X_poly = poly_reg.fit_transform(X)
lin_reg2 = LinearRegression()
lin_reg2.fit(X_poly, Y)
```

## :arrow_right: Visualizing the Polynomial Regression results
```
X_grid = np.arange(min(X), max(X), 0.1)
X_grid = X_grid.reshape((len(X_grid),1))
plt.scatter(X, Y, color = 'red', label = 'Scatter Plot')
plt.plot(X_grid, lin_reg2.predict(poly_reg.fit_transform(X_grid)), color = 'blue', label = 'Line Plot')
plt.title('Truth or Bluff (Polynomial Regression)')
plt.xlabel('Position Level')
plt.ylabel('Salary')
plt.legend()
plt.show()
```

## :arrow_right: Predicting a new result polynomial Regression
```
lin_reg2.predict(poly_reg.fit_transform(np.array(6.5).reshape(1,-1)))
```
