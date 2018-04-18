# CLT
Calculate sample stat and generalise to popn

Stat: mean; standard D; correlation

# Normal distribution
Relies on 2 parameters: mean and s.d.
if mean = mode = median, perfect gaussian normal distri

IQ ~ N(miu, sd) >> Notation

# plot in scipy
# Generate points on the x axis:
xpoints = np.linspace(40, 160, 500)

# Use stats.norm.pdf to get values on the probability density function for the Normal distribution
ypoints = stats.norm.pdf(xpoints, 100, 15)

# initialize a matplotlib "figure":
fig, ax = plt.subplots(figsize=(8,5))

# Plot the lines using matplotlib's plot function:
ax.plot(xpoints, ypoints, linewidth=3, color='darkred')

# 68, 95, 99.7 rule


    . 68% of observations from a population will fall within ±1±1 standard deviation 	of the population mean.
    . 95% of observations from a population will fall within ±2±2 standard deviations of the population mean.
    . 99.7% of observations from a population will fall within ±3±3 standard deviations of the population mean.

# Z-score
how many SD away obsservation is away from popn mean?

Z distribution allows for calculation of area under curve

Z = X - mu / sigma

CLT: sample mean will be approx normally distributed for large **sample size** regardless of distribution we are sampling


This distribution, the sampling distribution of X¯X¯, is Normally distributed even if the distribution of XX is not.

sample size must be at least **30**

SAMPLE Z is mu - sigma/ sigma / root.n
