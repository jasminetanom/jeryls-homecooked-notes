# Naive bayes
A naive bayes algo assumes that the presence (or absence) of a particular feature of a class is unrelated to the presence (or absence) of any other feature given a class

unrelated: all features independently contribute to the probability of a particular class

spam/not spam classification

# generative model
naive bayes is generative based on joint probability 
generate typical members of each class since we know how it looks like

discriminative is like hotdog not hotdog

# Bayes theorem

P(class|features)=P(features|class)P(class)
					/ P(features)

We can compute P(features|class) from training data


P(S|X1,...,Xn) = P(X1,...,Xn|S)
                =================
             P(X1,...,Xn|S)+P(X1,...,Xn|¬S)


# Laplace smoothing
Certain features have probabilities close to 0, use laplace smoothing

or use underflow (log probabilities)



