[Think Stats Chapter 8 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77) (scoring)
<pre>
def ExpSimulator(n=7, lam = 2, iters=1000):  
    means = []  
    for _ in range(iters):  
        xs = np.random.exponential(1.0/lam, n)  
        L = 1 / np.mean(xs)  
        means.append(L)  
    
    cdf = thinkstats2.Cdf(means)  
    thinkplot.Cdf(cdf)  
    thinkplot.Config(xlabel='Sample L Estimate', ylabel='CDF')
    
    ci = cdf.Percentile(5), cdf.Percentile(95)  
    print('The 90% Confidence Interval is:' , ci)  
    print('rmse L', RMSE(means, lam))  

ExpSimulator()  
</pre>
**Output:  
The 90% Confidence Interval is: (1.1765411024847683, 4.13593779838711)  
rmse L 1.060198078232754  
_Jupyter Notebook includes plot the sampling distribution of the estimate L_**
