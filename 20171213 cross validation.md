# Cross validation

# Hold out method: Train/test split

Split data into training and test set and use test to estimate error of trained classifier.

60-80% training
20-40% test

# normalisation
1. normalise then segment
2. segment then normalise 
3. normalise using training mean and s.d.
*Flag: test set accracy very high


> if test set is very different from training, consider UPDATING training set

*RANDOMISE BEFORE DOING TRAIN TEST SPLIT


# K-folds cross validation
Decide K value
1. split data into number of folds (K) first randomly
2. K = number of experiments

# Train validation test split
train test split 70/30

train validate split 70 (70/30)

test and validate do not take part in training

Procedure: 
1. divide into train, validation, test
2. model type and training parameters (k)
3. Train model using training set
4. evaluate using validation set
5. repeat 2-4 selecting different architectures models and tuning parameters
6. Select the best model
7. access model with final testing set


> This requires a much larger dataset

# holdout method
Train test split

test = holdout set

training set subject to K - fold cross validation

# Leave One Out (LOO) cross validation
K fold but k = N
N experiments, test = i

