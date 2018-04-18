# Regression

variables need to be continuous

simple Linear (one x) : Y = b1x1 + b0

multinomial: Multiple dependent variables (ys)

	y1 + y2 = b1x1 + b2x2 + b0 (multi linear and multi nomial)

variables:
 - dependent : output, y in simple and multi linear reg
 - independent: input

# Checking if mean is prediction
add hori line y = mean(x) to prediction


# adding the error term, epsilon
y = b1x1 + b0 + e to model imperfection

# Best fit
Residual Sum of Squares
RSS = sum (Yi - Yi hat)2

MSE : Mean squared error, indication of goodness of fit

=> fitting the regression line


# patsy
y, X = patsy.dmatrices('weight_lb ~ height_ctr -1', data=baseball, return_type='dataframe')

weight > y
height > x