# Ensemble

1. average probability
2. Plurality/majority voting
Binarise majority, then choose majority votes for classification
3. Bagging (Bootstrap Aggregating), no emphasis on misclassification; base model must not give you crap - > run models on unbiased samples [Reduce variance]
4. Boosting (Built sequentially, weak models) - > run models on biased samples [Reduce bias]
5. Stacking

# Random forests
2 sources of randomness
1. bootstrap
2. feature bagging