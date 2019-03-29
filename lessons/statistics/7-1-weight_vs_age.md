[Think Stats Chapter 7 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2008.html#toc70) (weight vs. age)
<pre>
ages , weights = live.agepreg , live.totalwgt_lb  
thinkplot.Scatter(ages, weights)  
thinkplot.Show(xlabel='Age (years)', ylabel='Weight (kg)')  
</pre>
**Output: _Jupyter Notebook shows scatterplot of weight vs. age_**  
<pre>
bins = np.arange(10, 45, 5)  
indices = np.digitize(live.agepreg, bins)  
groups = live.groupby(indices)  
mean_ages = [group.agepreg.mean() for i, group in groups]  
cdfs = [thinkstats2.Cdf(group.totalwgt_lb) for i, group in groups]  
for percent in [75, 50, 25]:  
    weight_cdf = [cdf.Percentile(percent) for cdf in cdfs]  
    label = '%dth' % percent  
    thinkplot.Plot(mean_ages, weight_cdf, label=label)  
thinkplot.Show(xlabel='Age (years)', ylabel='Weight (kg)', axis=[10, 45, 0, 16])  
</pre>
**Output: _Jupyter Notebook shows percentile plots of 25th, 50th, and 75th weight percentiles vs. age for_**  
<pre>
print('Pearson\'s correlation is: ' , Corr(ages,weights))  
print('Spearman\'s correlation is: ' , SpearmanCorr(ages,weights))
</pre>
**Output:  
Pearson's correlation is:  0.06883397035410908  
Spearman's correlation is:  0.09461004109658226**

