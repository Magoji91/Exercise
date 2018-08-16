# Exercise

Cross-tabulation: For categorical data (and quantitative data with only a few different values) an extension
of tabulation called cross-tabulation is very useful. For two variables, cross-tabulation is
performed by making a two-way table with column headings that match the levels of one variable
and row headings that match the levels of the other variable, then filling in the counts of all
subjects that share a pair of levels. The two variables might be both explanatory, both outcome,
or one of each. Depending on the goals, row percentages (which add to 100% for each row),
column percentages (which add to 100% for each column) and/or cell percentages (which add to
100% over all cells) are also useful.

Obs.: Cross-tabulation can be extended to three (and sometimes more) variables by making separate
two-way tables for two variables at each level of a third variable.

ANOVA: For one categorical variable (usually explanatory) and one quantitative variable (usually outcome),
it is common to produce some of the standard univariate non- graphical statistics for the
quantitative variables separately for each level of the categorical variable, and then compare the
statistics across levels of the categorical variable. Comparing the means is an informal version
of ANOVA. Comparing medians is a robust informal version of one-way ANOVA. Comparing
measures of spread is a good informal test of the assumption of equal variances needed for valid
analysis of variance.

Correlation and covariance: For two quantitative variables, the basic statistics of interest are the sample co- variance and/or
sample correlation, which correspond to and are estimates of the corresponding population
parameters. The sample covariance is a measure of how much two variables “co-vary”, i.e., how
much (and in what direction) should we expect one variable to change when the other changes.

Sample covariance is calculated by computing (signed) deviations of each
measurement from the average of all measurements for that variable. Then
the deviations for the two measurements are multiplied together separately for
each subject. Finally these values are averaged (actually summed and divided by
n-1, to keep the statistic unbiased). Note that the units on sample covariance are
the products of the units of the two variables.

Obs.: Positive covariance values suggest that when one measurement is above the mean the other
will probably also be above the mean, and vice versa. 

Obs.: Negative covariances suggest that when one variable is above its mean, the other is below its mean. And covariances near zero suggest that the two variables vary independently of each other.

Obs.: Technically, independence implies zero correlation, but the reverse is not necessarily true.

The correlation has the nice property that it is always between -1 and +1, with -1 being a “perfect” negative
linear correlation, +1 being a perfect positive linear correlation and 0 indicating that X and Y
are uncorrelated. The symbol r or rx,y is often used for sample correlations.

Age<-c(38,62,22,38,45,69,75,38,80,21,51)
Str<-c(20,15,30,21,18,12,14,28,9,22,20)
cor(Age, Strength)
cov(Age, Strength)


