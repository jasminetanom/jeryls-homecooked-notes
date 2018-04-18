# frequentism
count frequency then infer probability

# Bayesian
have a prior believed 'probability distribution' about the data 

more of conditional probability given that something has happened

prior
posterior
likelihood

More specifically:

    .. I have 100 observations, or data points, that I will use to update my "prior" belief about the height.
    .. I have collected fixed data, which I use to update my belief regarding the likelihood of different mean heights. This is called the posterior distribution of mean heights.
    .. Thus, I have a probability distribution of values for the mean height of professional male athletes.



# Frequentism
Frequentists have a different perspective on probability. As a Frequentist, I believe that:

    .. The mean height of male professional athletes is an unknown-but-fixed, "true" value.
    .. My 100 data points are a random sample from the total population of professional male athletes. That is to say, I have collected at random 100 possible height measurements from the population.
    .. This random sample is one of an infinite number of hypothetical samples. The procedure is considered infinitely repeatable. My inferences about height will be based on the idea that this sample is just one of an infinite number of hypothetical population samples.

# Conditional probability
Use probability tree

					0.9 +
    0.01 cancer
					0.1 -
.
					0.05 +
    0.99 no cancer
					0.95 - 


P(cancer | +) = P( + | cancer) . P(cancer)
				---------------------------
				           P(+)

# Bayesian stats
P(titre| data) = P(data|titre) x P(titer)
					-------------------
							P(data)


Posterior dist = likelihood x prior
					--------------
					P(data) or P(data|model)

1. specify model for data dets likelihood
2. specify a prior denominator
3. posterior distribution