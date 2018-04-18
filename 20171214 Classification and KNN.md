# Classification 
logistic regression is a classifier
Use to bench mark classifying

Regression -- > best fit line, no separation

Classification --> class boundary separates classes. boundary no need to be linear. but beware of overfit

# KNN 
specify k = integer
find k neighbours. majority wins

majority vote might change with k.

cannot be used as a benchmark

euclidean distance, draw line from A to B

KNeighborsClassifer() --- Sk learn. 

euclidean: pythagorus theorum
manhattan distance: sum of absolute value of differences

bcw['malignant'] = bcw['malignant'].map(lambda x: 0 if x == "B" else 1)

.value_counts() to check class proportions. not ok if 1 class is 70%

# Heat map without upper triangle

mean_corr = bcw.drop('id', axis=1).corr()

# Set the default matplotlib figure size:
fig, ax = plt.subplots(figsize=(9,7))

# Generate a mask for the upper triangle (taken from seaborn example gallery)
mask = np.zeros_like(mean_corr, dtype=np.bool)
mask[np.triu_indices_from(mask)] = True

# Plot the heatmap with seaborn.
# Assign the matplotlib axis the function returns. This will let us resize the labels.
ax = sns.heatmap(mean_corr, mask=mask, ax=ax)

# Resize the labels.
ax.set_xticklabels(ax.xaxis.get_ticklabels(), fontsize=14)
ax.set_yticklabels(ax.yaxis.get_ticklabels(), fontsize=14)

# If you put plt.show() at the bottom, it prevents those useless printouts from matplotlib.
plt.show()

# Pair plot

# set the seaborn style to have a white background
sns.set(style="ticks", color_codes=True)

# This function does a pairplot across your variables with the color
# set as the outcome "malignant" class variable
def bcw_pairplotter(df, variables, sample_frac=0.3):
    # sample_frac lets you specify an amount of the data to sample for the plot.
    # this speeds up the function which can take awhile with the full data.
    
    # get the number of rows/data points:
    rows = df.shape[0]
    
    # get downsample indicies for the data, if specified
    if sample_frac < 1.0:
        sample_inds = np.random.choice(range(0,rows), 
                                       size=int(round(rows*sample_frac)), 
                                       replace=False).astype(int)
    
    # make the pairplot for the variables:
    pairs = sns.pairplot(df.iloc[sample_inds, :], 
                         vars=variables, 
                         hue="malignant", 
                         palette=sns.xkcd_palette(['windows blue', 'amber']))

# get out the column variable names to put into the pairplotter function
colvars = [x for x in bcw if x not in ['id','malignant']]

bcw_pairplotter(bcw, colvars)


# Stratification 
for imbalanced datasets, must do stratified K fold to get equal proportion of classes

.fit (TRAIN)
.score (TEST)

.predict

# Accuracy 
overall accuracy is misleading, accuracy is ok for balanced datasets.

show precision, recall and F1

# baseline
% of majority class
classifier must beat baseline %

