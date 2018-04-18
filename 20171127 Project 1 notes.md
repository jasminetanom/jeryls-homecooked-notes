# Plotting sampling distribution
single_mean = np.mean(single)
single_sem = np.std(single)/np.sqrt(len(single))

# Generate points on the x axis:
xpoints = np.linspace(single_mean - single_sem*5, single_mean + single_sem*5, 250)

# Use stats.norm.pdf to get values on the probability density function for the normal distribution:
ypoints = stats.norm.pdf(xpoints, single_mean, single_sem)

# Initialize a matplotlib "figure:"
fig = plt.figure(figsize=(8,5))

# Get the current "axis" out of the figure:
ax = fig.gca()

# Plot the lines using matplotlib's plot function:
ax.plot(xpoints, ypoints, linewidth=3, color='darkred')
ax.axvline(single_mean, linewidth=4, ls='dashed', c='black')



    90%: The z-score multiplier should be z = 1.645, because 90% of the area under the Z N(0,1)Z N(0,1) normal distribution lies between -1.645 and 1.645.
    95%: The z-score multiplier should be z = 1.96, because 95% of the area under the Z N(0,1)Z N(0,1) normal distribution lies between -1.96 and 1.96.
    99%: The z-score multiplier should be z = 2.575, because 99% of the area under the Z N(0,1)Z N(0,1) normal distribution lies between -2.575 and 2.575.


values are values under the standard normal distribution curve