A.T (T stands for transpose)
Mean

numpy.mean(a, axis=None, dtype=None)

    a: array containing numbers whose mean is required
    axis: axis or axes along which the means are computed,
        default is to compute the mean of the flattened array
    dtype: type of data to be used in calculations

Median

numpy.median(a, axis=None, out=None)

    a: array containing numbers whose median is required
    axis: axis or axes along which the median is computed
        default is to compute the median of the flattened array
    out: alternative output array to place the result, must have the same shape and buffer length as the expected output.

Mode

scipy.stats.mstats.mode(a, axis=0)

    a: array containing numbers whose mode is required
    axis: axis or axes along which the mode is computed
        default is 0
        if None, compute the mode of the flattened array

It returns (mode: array of modal values, count: array of counts for each mode).


Range

numpy.ptp(a, axis=None, out=None)

'ptp' stands for 'peak to peak'.

    a: array containing numbers whose range is required
    axis: axis or axes along which the range is computed,
        default is to compute the range of the flattened array.

It returns a new array with the result.


Variance

Variance can be calculated in python using different libraries like numpy, pandas, and statistics.

numpy.var(a, axis=None, dtype=None, ddof=0)

    a: array containing numbers whose variance is required
    axis: axis or axes along which the variances are computed, default is to compute the mean of the flattened array
    ddof : int, optional
        ddof stands for delta degrees of freedom. It is the divisor used in the calculation, which is N - ddof, where N is the number of elements.
        The default value of ddof is 0.


Standard Deviation

...the square root of variance.

It can be calculated in python using different libraries like numpy, pandas, and statistics.

numpy.std(a, axis=None, dtype=None, ddof=0)

Parameters are the same as numpy.var().

    a: array containing numbers whose standard deviation is required
    axis: axis or axes along which the standard deviations are computed, default is to compute the mean of the flattened array
    ddof : int, optional
        ddof stands for delta degrees of freedom. It is the divisor used in the calculation, which is N - ddof, where N is the number of elements.
        The default value of ddof is 0


Skewness

scipy.stats.skew(a, axis=0)

For normally distributed data, the skewness should be about 0. A skewness value > 0 means that there is more weight in the left tail of the distribution.

Seaborn must be used in conjuncture with matplotlib
import seaborn as sns
import matplotlib.pyplot as plt
%matplotlib inline >>> adds output in notebook

BOX PLOT
sns.boxplot(data=tips.drop(['size'], axis=1))

uci data analysis websites

Loading and describing data solutions

important function:
d = {key_name:[row[index] for row in data] for index, key_name in enumerate(names)}

