# R in kaggle

## Evaluation matrix
AU(RO)C: area under receiver operating characteristic curve (confusion matrix) - only applied on binary classification
calculate specificity (X axis) and sensitivity (Y axis)

Plot curve according to cutoff values
Range of AUC = 0.5 to 1. 0.5 means dumb model

1. download data set (Train, test, submission)
submission ID, prediction. submission id must match test id

2. Timeline: first submission, merger, final submission

3. SOP
READR, XGBOOST, CARET, MLMETRICS, BINR, DPLYR, GGPLOT2
pandas, sklearn, k fold validation, numpy eval matrix, even bins, data manipulation, matplotlib

check row ids, submission, make copy of train set responses, outcomes
check for missing data
check for valid data types (integer, categorical, numerical, boolean, data)
check for unique values
run the near zerovar caret, remove zero variance features

patsy categorical variables, choose influential category.
usually use if category has 0.01% of population

# Random forest model
Make different trees based on binary choices, calculate using entropy

# Extreme gradient boosting
similar to random forest but using gradient descent/ascent

# Ranking up in kaggle
1. cross validation
hold out 70/30
k fold
leave one out

2. features engineering (one hot encoding/patsy)
log score or z score transformation
binarised
recode
quadratic discriminant analysis
entropy
hashing

3. Tune model
regression based, regularisation
tree based, depth, n trees, leafs, child etc
gradient boosting; learning rate, subsample, featuers sub sample, essian gradiant loss fx, n rounds, gamma, max depth

4. Ensemble 
dark art
white magic

# Tune hyper params for XGboost
1. eta; default = 0.3 learning rate
standard 0.005 - 0.05 (step 0.005)

2. colsample_bytree; default = 1
number of features to consider for building tree
standard 0.15 - 0.85 (step 0.05)

3. subsample; default = 1
random selection of samples for building model
0.70 - 0.95 (step 0.05)

4. max_depth; default = 6
maximum depth of tree
4-20 (step 1)
higher values will overfit, monitor CV, and computational speed

5. scale_pos_weight; default = 1
useful for imba dataset
scaled to ratio of neg/pos

Advanced
6.  min_child_weight; default = 1
minium sum of instance weight
0-10 (step 1)

7. gamma; default = 0
minimum loss reducation to create leaf note, pseudo regularisation
0-20 (0.1, 0.01, 1)

8. eval_metric

9. objective

# Feature engineering
one hot encoding (get dummies/patsy)

log scale transformation (large numbers)

Z score transformation

Binarised features ** more impt

pairwise linear features, 2 features to create new featuer

higher order polynomial features

# Ensembling
different models definition
differnet seed
combinations of different hyperparam
algo: GLMNET, ENET, NNET, RF, XGBOOST, RLIGHTGBM etc

dark art
levearaging on all submissions
rank averaging
weighted averaging

white magic
model based approach to ensemble(100 models at least)
preict train + test dataset
model predictions are used as new features
blended approach- use model predictions + original data featuers to build next stage predictions
multi stage, usually 3rd 4th is dark art averaging
stage 1 : build 100 models
stage 2 : stack predictions
stage 3 : dark art averaging