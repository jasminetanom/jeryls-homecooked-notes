# Bayesian Estimation and regression

Bayes theorem links 2 conditional probabilities

Posterior: Likelihood times prior

# Work flow
with pm.Model() as model:
    
    usa_mean = pm.Normal('usa_mean', prior_mean, sd=50)
    euro_mean = pm.Normal('euro_mean', prior_mean, sd=50)
    
    usa_std = pm.Gamma('usa_std', mu=prior_std, sd=50)
    euro_std = pm.Gamma('euro_std', mu=prior_std, sd=50)
    
    usa_mpg = pm.Normal('usa_mpg', mu=usa_mean, sd=usa_std, observed=american_mpg)
    euro_mpg = pm.Normal('euro_mpg', mu=euro_mean, sd=euro_std, observed=european_mpg)
    
# get deterministic
    mean_delta = pm.Deterministic('mean_delta', usa_mean - euro_mean)
    std_delta = pm.Deterministic('std_delta', usa_std - euro_std)
    effect_size = pm.Deterministic('effect_size', mean_delta / np.sqrt((usa_std**2 + euro_std**2)/2.))

# Sampling to get exact distribution
with model:
    step = pm.NUTS()
    start = pm.find_MAP()
    trace = pm.sample(50000, start=start, step=step, njobs=4)

# plotting distributions
pm.plot_posterior(trace[5000::3],
                  varnames=['usa_mean', 'euro_mean',
                            'usa_std', 'euro_std'],
                  color='#87ceeb')
