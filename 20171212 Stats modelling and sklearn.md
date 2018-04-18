# Stats modelling
sklearn > machine learning
statsmodel > statistics

sklearn (python) / caret (R)
1. linear reg
2. log reg
3. support vector machines
4. classification and decision trees
5. naive bayes , spam or not spam
6. clustering models, k means, hierachical, db scan

7. model eval and selection
8. preprocessing
9. nlp : gensim nltk
10. dimensionality reduction: BCA

# Steps for sklearn
from matplotlib import pyplot as plt
import seaborn as sns

from sklearn import datasets, linear_model
from sklearn.metrics import mean_squared_error

# Don't forget to turn on plotting display in the notebook
%matplotlib inline 

Training (fit) and target datasets must always match in length!

# Linear regression with sklean
lm = linear_model.LinearRegression()

X = df[["RM"]]
y = target 

model = lm.fit(X, y)

# predictions
predictions  =  model.predict(X), # predict a test set not training set
score        =  model.score(X, y)

# Plot the model
plt.figure(figsize=(8,8))
plt.scatter(predictions, y, s=30, c='r', marker='+', zorder=10)
plt.xlabel("Predicted Values from RM - $\hat{y}$")
plt.ylabel("Actual Values MEDV - y")
plt.show()

print "score: ", score

# sklearn attributes

    .coef_: property containing the coeffients for the predictor variables
    .intercept_: value of the intercept
print model.coef_
print model.intercept_

> A 1 unit increase in variable RM corresponds to a 9.10 unit increase in the estimate of MEDV


# Metrics for evaluation
different model uses different metrics

regression = RMSE ~ MSE
from sklearn.metrics import mean_squared_error

print np.sqrt(mean_squared_error(target, predictions))

# MLR
lm = linear_model.LinearRegression()

X = df[["RM","LSTAT"]].values
y = target 

model = lm.fit(X, y)

predictions  =  model.predict(X)
score        =  model.score(X, y)


# Plot the model
plt.figure(figsize=(8,8))
plt.scatter(predictions, y, s=30, c='r', marker='+', zorder=10)
plt.xlabel("Predicted Values from RM + LSTAT - $\hat{y}$")
plt.ylabel("Actual Values MEDV - y")
plt.show()

print "score: ", score

# Statsmodel prediction
import statsmodels.api as sm

X = df[["RM","LSTAT"]].values
# manually add the intercept column:
X = np.concatenate([X, np.ones((X.shape[0], 1))], axis=1)
y = target

model = sm.OLS(y, X)
model = model.fit()
predictions = model.predict()

# model summary
model.summary()

# Patsy
import patsy

formula = 'CRIM ~ TAX + AGE + ZN'
> y tilde x variables

y, X = patsy.dmatrices(formula, data=df, return_type='dataframe')
