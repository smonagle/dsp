[Think Stats Chapter 3 Exercise 1](http://greenteapress.com/thinkstats2/html/thinkstats2004.html#toc31) (actual vs. biased)

"numb_child = Counter(resp['numkdhh']) \n"
child_hist = thinkstats2.Hist(numb_child)
pmf = thinkstats2.Pmf(child_hist, label='actual')
child_hist

**Output** Hist({3: 666, 0: 3563, 2: 1500, 1: 1636, 4: 196, 5: 82})

biased_pmf = BiasPmf(pmf, label='observed')
thinkplot.PrePlot(2)
thinkplot.Pmfs([pmf, biased_pmf])
thinkplot.Config(xlabel='Number of Children', ylabel='PMF')



