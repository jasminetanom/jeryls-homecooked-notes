# Support vector machines (SVM)
boundary (Black line) and margin (dotted)
tilt the boundary until margin is maximum. Drawing a river. Maximising margins from boundary. (Maximum margin hyperplane)

Classification: minimise intra distance, maximise inter distance

Support vectors are data points that hits the margin at maximum distance

# linear and not linear seperable
linearly separable: can draw linear straight line as decision boundary
not linearly separable: cannot draw straight line/plan

# Hyperparam C
regularization hyper param

#Kernels
Linear
Polynomial
Guassian gamma
radial basis function, gamma





# Classification and regression trees (CARTS) /  Decision trees / recurssive partionining
Split ONLY in recti-linnear fashion

Root node, leaf node (no more further splits)

Overfits very easily

# leaf nodes
nodes will stop once it has achieved purity

prune the tree so it doesnt grow excessively
1. grow then cut
2. put in a box (depth/layers)

# algos to build trees
Types: 
a. greedy
b. recursive
c. local optimum

1. hunts (greedy recursive optimum)

# Splitting
splitting is based on gain, no way there is a loss

# Purity
Differs across algos
1. entropy
2. gini impurity (NOT INDEX) - binary only [CART uses gini]
3. classification error

When I is the entropy, this quantity is called the information gain.

# Restrictions (pruning)
CART
C4.5
ID3, information gain based on decision

# Decision tree regression

pediction rather than classify

We cannot therefore use the same measure of purity we used for classification. Instead we look to minimize the Sum of Square Errors at each split


PERFORM TREE THEN FIND FEATURE IMPORTANCE

Feature importance: ranks variables according to importance, from most important to least importance