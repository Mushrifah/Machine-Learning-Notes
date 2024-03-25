  
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

----------------------------------------------------------------------------------------------------------------

# Decision tree regression

- data is splitted based on SSR (sum of residuals) = (yi - ymean)^2

    -> lesser the SSR the more likely it is split and taken as initial root node

    -> tries different combinations of splits and calculates the SSR for all and choose the one with min value

- TreeScore(T) = SSR + alpha*|T~| (tree complexity penalty), alpha-> complexity parameter , T -> number of leaf or terminal nodes

- alpha -> best value choosen with hyperparameter tuning

----------------------------------------------------------------------------------------------------------------

# Decision tree classification:

- predict a categorical value based on independent variables, tree like structure with split conditions

- classification tree algos use a mathematical formula as a measure of degree of impurity within a partition

- impurity -> level of randomness or disorder within a partition

- low impurity -> large homogenity(similarity) & high impurity -> heterogeneity(dissimilarity)

    - Entropy (C5.0) -> [sum(i=1-c) -pi * log2(pi)] , c->no.of class, i-> class level, pi-> probability/proportion of values

        - calculate Entropy(S1) = [sum(i=1-c) -pi * log2(pi)]

        - calculate Entropy(S2) = [sum(i=1-n) wi*Entropy(Pi)] -> after split

        - Information gain = Entropy(S1) - Entropy(S2) -> combined difference of entropy after and before the split

    - Gini -> used by CART -> measure of statistical dispersion

        - Gini(S) = 1 - [sum(i=1-c) Pi^2]

- Data is recursively split into smaller subsets until:

    - all data in partition are of the same class

    - all features have been exhausted

    - a specified tree size limit or other user-defined condition has been met

- Overfitting occurs when a decision tree fits our data too perfectly

    - pre-pruning -> set a condition to limit size of tree

    - post-pruning -> limit size of tree after recursive partitioning process
