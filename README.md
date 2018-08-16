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
cor(Age, Str)
cov(Age, Str)
sd(Age)
sd(Str)

OBS.: Side-by-side boxplots are the best graphical EDA technique for examining the relationship between a categorical variable and a
quantitative variable, as well as the distribution of the quantitative variable at each level of the categorical variable.

boxplot(Age)
boxplot(Str)

OBS.: In a nutshell: You should always perform appropriate EDA before further analysis of your data. Perform whatever steps are necessary to become more familiar with your data, check for obvious mistakes, learn about variable distributions, and learn about relationships between variables. EDA is not an exact science – it is a very important art!

Degrees of freedom:represent the number of independent pieces of information that go into the calculation of the statistic,
Obs.: "...as long as all five deviations are the same, the variance will be the same. This make sense because variance is a pure measure of spread, not affected by central tendency. But by mathematically rearranging the definition of mean, it is not too hard to show that the sum of the deviations (not squared) is always zero."
Obs.: "In general, a variance or standard deviation calculated from n data values and one mean has n − 1 df."

Residuals: the difference between any data point and the regression line, they are sometimes called “errors.” Error in this context doesn’t mean that there’s something wrong with the analysis; it just means that there is some unexplained difference. In other words, the residual is the error that isn’t explained by the regression line.

The residual(e) can also be expressed with an equation. The e is the difference between the predicted value (ŷ) and the observed value. The scatter plot is a set of data points that are observed, while the regression line is the prediction.

Residual = Observed value – predicted value
         e = y – ŷ
         
Obs.: The sum of the residuals always equals zero
      The mean of residuals is also equal to zero, as the mean = the sum of the residuals / the number of items. The sum is zero, so 0/n will always equal zero.
      
 p-value: probabilidade obter uma estatística de teste = ou + extrema daquela observada na amostra. 
 Ho - hipótese nula
 Ha - Alternativa
 
                  #A hipótese H0 é verdadeira	 // A hipótese H0 é falsa
Rejeita-se H0	 /  Erro do tipo I	            //  sem erro
Não se rejeita /  H0	sem erro	              //  Erro do tipo II

lm(formula = Age ~ Str)

Obs.: Por exemplo, vamos supor que o nível de significância foi fixado em {\displaystyle \alpha } \alpha = 0,05. Um valor-p igual a 0,20 indica que nós teríamos rejeitado H0 se tivéssemos escolhido um nível de significância de 0,20, ao menos. Como escolhemos {\displaystyle \alpha } \alpha = 0,05, não rejeitamos H0. Isto leva a uma regra simplista, mas usual, onde rejeitamos H0 se o valor-p é menor que {\displaystyle \alpha } \alpha e não rejeitamos H0 caso contrário.

A small p-value (typically ≤ 0.05) indicates strong evidence against the null hypothesis, so you reject the null hypothesis.

A large p-value (> 0.05) indicates weak evidence against the null hypothesis, so you fail to reject the null hypothesis.

p-values very close to the cutoff (0.05) are considered to be marginal (could go either way). Always report the p-value so your readers can draw their own conclusions.

Obs.:You randomly sample some delivery times and run the data through the hypothesis test, and your p-value turns out to be 0.001, which is much less than 0.05. In real terms, there is a probability of 0.001 that you will mistakenly reject the pizza place’s claim that their delivery time is less than or equal to 30 minutes. Since typically we are willing to reject the null hypothesis when this probability is less than 0.05, you conclude that the pizza place is wrong; their delivery times are in fact more than 30 minutes on average, and you want to know what they’re gonna do about it! (Of course, you could be wrong by having sampled an unusually high number of late pizza deliveries just by chance.)

Coefficient - t value: measure of how many standard deviations our coefficient estimate is far away from 0. We want it to be far away from zero as this would indicate we could reject the null hypothesis - that is, we could declare a relationship between speed and distance exist. In our example, the t-statistic values are relatively far away from zero and are large relative to the standard error, which could indicate a relationship exists. In general, t-values are also used to compute p-values.

Resume: t-test, used to determine whether the means of two groups are equal to each other.

t.test(Age,Str)


The null hypothesis is that the two means are equal, and the alternative is that they are not. 

Residual Standard Error: measure of the quality of a linear regression fit. Theoretically, every linear model is assumed to contain an error term E. Due to the presence of this error term, we are not capable of perfectly predicting our response variable (dist) from the predictor (speed) one. The Residual Standard Error is the average amount that the response (dist) will deviate from the true regression line.

The R-squared (R2): statistic provides a measure of how well the model is fitting the actual data. It takes the form of a proportion of variance.

Obs.: It always lies between 0 and 1 (i.e.: a number near 0 represents a regression that does not explain the variance in the response variable well and a number close to 1 does explain the observed variance in the response variable). 

F-statistic is a good indicator of whether there is a relationship between our predictor and the response variables. The further the F-statistic is from 1 the better it is. However, how much larger the F-statistic needs to be depends on both the number of data points and the number of predictors. Generally, when the number of data points is large, an F-statistic that is only a little bit larger than 1 is already sufficient to reject the null hypothesis (H0 : There is no relationship between speed and distance). 

Reject the null when your p value is smaller than your alpha level. You should not reject the null if your critical f value is smaller than your F Value, unless you also have a small p-value.

anova(ex)
