# Time series

Issue of stationarity: mean and variance are same throughout

Issues:
observations not independent

# rolling function
mean of moving window for example
Rolling mean

there's ARMA (auto reg, moving average)
there's rolling mean average model

# Rolling mean
yearly = data['unemployment_rate'].resample('A').mean().rolling(window=3, center=False).mean()
yearly.head()

window = number of entries
center = True/false, false takes preceding window, true takes current as centre

# Expanding mean
no window size, present plus all preceding
decay, previous values

# Models
1. Moving average
2. Auto regress
3. ARMA combine (p,q)
4. ARIMA I(integrated) (p,d,q,)

# Workflow
1. visulaise:
detrend/ seasonality
2. stationise : transformation, deflation/logarithm/first difference/seasonal difference/seasonal adjust
[test] = dickey fuller test, null is unique root in data
3. plot acf/pacf
4. build arma
5. tune?

params 
p = non seasonal AR order
d = non seeasonal diff
q = non seasonal MA order
P = seasonal AR order
D = seasonal diff
Q = seasonal MA order m =  number of periods per season


Read up: wavelets, fourier transformation, 

# Evaluation
1. plot residual
2. Ljung Box test
3. Akaike information criteria (AIC)