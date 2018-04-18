# Recommender systems

Recommend without you searching for it
Order is customised whenever possible

# how to build

1. Similar people (collaborative)
2. similar items (content based)

Problems:
1. frequent likes
2. cold start(not enough user data)
3. adding likes later into system
4. sparsity: purchases make small percentage of catalogue
5. scalibility: cosine (1 mil vs 1mil vector for eg)

# User based collaborative filtering
find your doppelganger
cosine similarity: cosine(0 deg) = 1 (similar)
cos 90 deg = 0 (dissimilar)
cos 180 deg = -1 opposite
(similar to uncentered correlation coeeff) / mean centred= pearson corr coeff
mean centering takes mean of filled values and corrects these values

cosine similarity affected by 0s (as na)

# Jaccard distance
1 - (#of brands in common/# of brands)

