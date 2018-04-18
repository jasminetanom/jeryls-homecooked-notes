# EDA workflow
> Standard workflow
1. clean
2. EDA
3. Build Model

# 1. Look at metadata, data dictionary

# 2. .head, .dtypes

# 3. drop unwanted columns
boston.drop('uUnnamed:0', axis=1, inplace=True)
OR
use readcsv to read index
pd.read_csv(csv, index_col=0)

# 4. Clean corrupted columns (columns with dtype object)
check .values
use map functions

# 5. check isnull
df.isnull().sum()

# 6. drop null
df.dropna(inplace=True), rows with Null

# 7. make columns more descriptive
.rename(columns={
	'col1': 'newname',
	..
	..
	..}, inplace=True)

# 8. .describe()

# 9. boxplots
fig = plt.figure(figsize=(x,y))
ax= fig.goa()

ax = sns.boxplot(df.col, orient='v', fliersize=8, linewidth=1.5, notch=True, saturation=0.5, ax=ax)

ax.set_ylabel('rate of crime', fontsize=16)
ax.set_title('skfdfjd', fontsize=16)

Outliers: more than 1.5 IQR. minorities/fraud

# 10. plot all boxplots

fig = plt.figure(figsize=(x,y))
ax = fig.goa()

ax= sns.boxplot(data=boston, orient='h', fliersize=5, linewidth = 3, notch=True, saturation=0.5, ax=ax)

ax.set_title('dkfd')

# 11. Standardize for scale
roc = boston.rate_of_crim.values
roc_mean = np.mean(roc)
roc_std = np.std(roc)


standardized_var = (var - var_mean)/ std of var
roc_stand = (roc - roc mean)/ roc_std
**Do BOX AFTER STANDARDIZATION**

# 12. plot after standardisation
fig = plt.figure(figsize=(8,4))
ax = fig.goa()

ax= sns.distplot(roc_stand, bins=30, kde=True)

# 13. box after stand
bostonstand = (boston - bostoon mean/boston.std)
fig= plt.figure(figsize=(15,7))

ax = fig.goa()

ax = sns.boxplot(data=boston_Stand, orient='h', fliersize=5, linewidth=1, notch=True, saturation=0.5, ax=ax)

plt.show()


# 14 . Covariance
np.cov
pct_under = boston.pct_underclass.values
medval = boston.home_median.values

np.cov(pct_under, med_, bias=True) bias: / N for true N-1 for false

# 15. correlation
np.corrcoef(x, y, bias=True)

CORR MATRIX (look for strong colors, and white RCs)
df.corr()

plt.figure(figsize=(20,20))
sns.heatmap(df.corr(),)

