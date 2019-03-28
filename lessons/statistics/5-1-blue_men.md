[Think Stats Chapter 5 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2006.html#toc50) (blue men)

import scipy.stats  

mu = 178  
sigma = 7.7  
dist = scipy.stats.norm(loc=mu, scale=sigma)  
lower_bound = (5*12+10)*2.54  
upper_bound = (6*12+1)*2.54  
print(100*(dist.cdf(upper_bound) - dist.cdf(lower_bound)),'% of people are between 5\'10" and 6\'1"')  

**Output: 34.27468376314746 % of people are between 5'10" and 6'1"**

