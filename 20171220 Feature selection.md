# feature selection
# Filter method
set of features > select best subset > learning algo(ML) > performance
BEFORE ML (independent of ML)
 
- looks for correl in outcome

1. EDA > 2. Filter methods
Possible to use filter and wrapper

correlation methods:
				Continuous	Categorical (Response)
Continuous		Pearson'	Linear discriminant analysis
Categorical		Anova		Chi-square

anova: means of diff groups equal ?

Does not remove multicollinearity

# Wrapper method
hybridised with ML

set of features > selecting best subset(wrapper applied here with model building) > performance

combinatorial approach. long processing

1. forward selection 
start with no features, then add add add
2. backward elimination
start with all features then elmininate
3. recursive feature eliminiation
frequently combined with support vector machine (SVM)


Recursive Feature Elimination
from sklearn.feature_selection import RFE

# feature extraction 
model = LogisticRegression() 
rfe = RFE(model, 3)
fit = rfe.fit(X, Y) 
print("Num Features: %d") % fit.n_features_ 
print("Selected Features: %s") % fit.support_ 
print("Feature Ranking: %s") % fit.ranking_

# feature selection using lasso (applies to regression problems)
lambda can be tuned to set shrinkage level, higher the lambda the more coefficients shrunk

# multicollinear elimination
done BEFORE filter or wrapper
calculate VIF

https://etav.github.io/python/vif_factor_python.html

# random shuffling feature selection
1. calculate score
2. randomise order of values in column, if feature has predictive power, score becomes worse
3. if no change in score, toss feature

# grid search
running for loops to iterate through hyper params combination

# random search 
random search combinations for hyperparam

# set up my gridsearch parameters:
sgd_params = {
    'loss':['squared_loss','huber'],
    'penalty':['l1','l2'],
    'alpha':np.logspace(-5,1,25)
}

sgd_reg = SGDRegressor()
sgd_reg_gs = GridSearchCV(sgd_reg, sgd_params, cv=5, verbose=False) # grid search does mdodel and iterate through params

.fit

print sgd_reg_gs.best_params_
print sgd_reg_gs.best_score_
sgd_reg = sgd_reg_gs.best_estimator_