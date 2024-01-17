   
# Ordinary Least Squares (OLS):

- parametric method estimating parameters also called coefficients, that describes data relationships

- least squares:- method to find best fit by squaring the residuals and then minimize the sum of squares.

- BLUE -> Best linear unbiased estimator.  
- lower standard errors -> more certainity around the results.

- conditions that make OLS blue are called Gauss Markov Assumptions:-  
    - Linear parameters:- dependent variable must be continuously measured variable.  
    - exogeneity condition:- no correation between explanatory variables and error term (means X is an independent variable and Y depends on X.)  
        - exogenous: explanatory variable(X)  
        - endogenous: correlated with error term  (Y)  
    - homoscedasticity assumption:- variation of noise in the data must remain stable across the explanatory variables.  
    - Collinearity assumption:- explanatory variables should not be highly correlated with each other.

- Model fit metrics:  
    - TSS (Total sum of squares) = (y-y_mean)^2  
    - RSS(residual sum of squares) = Unexplained variation  
    - R-squared :- lies between 0-1  
	    = (TSS-RSS)/TSS   
	    = Explained variation/total variation  
	    = 1 - Unexplained variation/Total variation   
	    = 1 - RSS/TSS  
    - RSS decrease -> regression line was very close to actual points -> independent variable explain majority of variation in the target variable -> R-squared increase   
      
    - Adjusted R-squared :- penalizes the inclusion of unecessary variables -> u can add more predictors to the model and if increase then new variable improves the model performance  
	    = 1 - (1-R^2)(n-1)/(n-k-1)  
	    where R:- R-squared values , n:- no.of data points, k:- no. of independent variables

- regression with quadratic term:- additional squared explanatory variable can lead to a quadartic relationship with dependent variable -> both variables act like a quadratic equation

- Indicator variables:-   
    - these are categorical variables used (but they should be in the form of two categories only ie if 1 or 0 and if it is more than 2 categories then create different columns for each  category and fill it with binary value based on its occurence for each category. )  
    - these variables shift the regression lines up or down  
    - there should be a reference category for it to make sense of the indicator coefficients/variables

- Time can be used as variable in regression model.

- For Elasticities we use log transformations for variables.


----------------------------------

## Code in Python:

```python
from matplotlib import pyplot as plt
import seaborn as sns
```
