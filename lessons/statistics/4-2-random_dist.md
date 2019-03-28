[Think Stats Chapter 4 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2005.html#toc41) (a random distribution)

my_weight = 8.25  
live_cdf = thinkstats2.Cdf(live.totalwgt_lb, label='live')  
other_cdf = thinkstats2.Cdf(others.totalwgt_lb, label='other')  
print('My Percentile Rank among live births is:' , live_cdf.PercentileRank(my_weight))  
print('My Percentile Rank among others (>1 children) is:' , other_cdf.PercentileRank(my_weight))  

**Output:  
My Percentile Rank among live births is: 78.68997565833149  
My Percentile Rank among others (>1 children) is: 76.81283422459893**
