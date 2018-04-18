# Learning
1. Supervised: 		Y
2. Unsupervised:	no Y
3. Semi-supervised:	some Y (recommenders)

vif to check multiple relationship

# objectives of modelling
prediction: Predict y
inference: does variable x affect y

# Terms
[Bias, variance] = reducible error, irreducible error

Get reducible error to a minimum,
bias and variable move in opposite directions

# cubic interpolations often gives best results
morale_func = interp1d(weekpoints, moralepoints, kind='cubic') 

Low Bias: fitting model too close to a line
Low Variance: overfitting the model

# error
err(x) = bias2 + variance + irreducible error

# F Statistic (model.summary)
Value must be greater than 1. Response variable, at least one predictor is related to y

1. Check F stats
2. which X variables to use
3. Figure out beta coeffs

R^2 proportion of variance explained. = 1 means model is accurate if less than 1, add more variables to increase R^2

# Strategies to improve model
Variable subset selection: Choose set of variables that best predict y. forward/backward/hybrid

dimensional reduction: change to PCA components

shrinking coefficients of linear regression: reduce impact

# techniques of linear regressions
lasso
ridge
elastic net : ridge + lasso
pca
partial least sq

# Ridge parameter
lambda^2(sum(beta coeff^2))
lambda (0, infinity)
found using cross validation

Ridge: Reduce all coefficients
Lasso: Zeros certain coefficients

**Scale variables before doing regularization **


# Flow chart

1. standardize variables

wine.ix[:, nc] = (wine.ix[:, nc] - wine.ix[:, nc].mean()) / wine.ix[:, nc].std()

2. patsy the target and variables

# Get the non-target cols with a simple list comprehension
non_target_cols = [c for c in wine.columns if c != target]

# Use some string adding and joining to make the simple model formula:
formula_simple = target + ' ~ ' + ' + '.join(non_target_cols) + ' -1'   # -1 removes 1 col (row indexes)
print formula_simple

# Make the complex formula:
formula_complex = target + ' ~ (' + ' + '.join(non_target_cols) + ')**2 -1'
print formula_complex

# Create the X and Y pairs for both!
Y, X = patsy.dmatrices(formula_simple, data=wine, return_type='dataframe')
Yoverfit, Xoverfit = patsy.dmatrices(formula_complex, data=wine, return_type='dataframe')

Y = Y.values.ravel()
Yoverfit = Yoverfit.values.ravel()

# Determining alpha value
cross val technique
choose alpha that gives a good R^2 

# L1 ratio and alpha

L1 ratio is the ratio between lambda2(ridge) and lambda1(lasso)

L1 ratio = 0.5 to make it a enet

arvinder singh




