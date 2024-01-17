  
# Logistic regression

- Linear regression

    - Y=b0 + b1*X

    - linear relationship between predictor variable X and response Y

- Poisson Regression

    - log(Y)=b0 + b1*X

    - X and Y relationship is log-linear or exponential

- Logistic regression:

    - relationship between predictor variable X and response Y is binary or dichotomous

    - sigmoid curve fits the data well rather than linear when X is categorical.

    - Y = e^(b0+b1*X)/(1 + e^(b0+b1*X))

    - R2 = (LL(overall probability) - LL(fit))/(LL(overall probability)) where LL -> log likelihood

    - Chi-square value = 2(LL(fit) - LL(overall probability))




```python
from sklearn.linear_model import LogisticRegression
classifier = LogisticRegression()
model = classifier.fit(X_train, y_train)
model.predict(X_test)
model.score(X_test, y_test)

model.intercept_
model.coef_
log_odds = np.round(model.coef_[0], 2)
lodds = np.round(np.exp(log_odds), 2)
```

