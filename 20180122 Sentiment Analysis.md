# Sentiment analysis with spacy and vader

Build a library of sentiments (words that have positive meaning; negative meaning)
Score the text with your library
Advanced: Use a recursive tree model

Calculate objectivity:
objectivity = 1. - (positive_score + negative_score)


# Workflow
1. process data
2. do some feature engineering (like POS, proportion of POS)
3. Fit model 

# Vader package
Valence aware dictionary and sentiment reasoner
auto parse text

# Naive Bayes classifier
Mostly use to classify email spam

Given a feature xi and target yi, Naive Bayes classifiers solve for P(xi|yi)P(xi|yi). In other words, the probability of a feature/predictor given that the target is 1.

# BernoulliNB from sklearn
Use to classify binary targets

BernoulliNB(alpha=1.0, ... .. 
alpha: Laplace/Lidstone smoothing parameter, value of 0 or 1
if 1, smoothens out and avoid divde by 0 errors
