[Think Stats Chapter 9 Exercise 2](http://greenteapress.com/thinkstats2/html/thinkstats2010.html#toc90) (resampling)

_Pulled from textbook solutions_
<pre>
import hypothesis

class DiffMeansResample(hypothesis.DiffMeansPermute):    
    def RunModel(self):
        group1 = np.random.choice(self.pool, self.n, replace=True)
        group2 = np.random.choice(self.pool, self.m, replace=True)
        return group1, group2
 
 def RunResampleTest(firsts, others):
    data = firsts.prglngth.values, others.prglngth.values
    ht = DiffMeansResample(data)
    p_value = ht.PValue(iters=10000)
    print('\nmeans permute preglength')
    print('p-value =', p_value)
    print('actual =', ht.actual)
    print('ts max =', ht.MaxTestStat())

    data = (firsts.totalwgt_lb.dropna().values,
            others.totalwgt_lb.dropna().values)
    ht = hypothesis.DiffMeansPermute(data)
    p_value = ht.PValue(iters=10000)
    print('\nmeans permute birthweight')
    print('p-value =', p_value)
    print('actual =', ht.actual)
    print('ts max =', ht.MaxTestStat())

RunResampleTest(firsts,others)
</pre>

**Output:
means permute preglength  
p-value = 0.1661  
actual = 0.07803726677754952  
ts max = 0.20988956742235132  

**means permute birthweight  
p-value = 0.0  
actual = 0.12476118453549034  
ts max = 0.11243783713556343
