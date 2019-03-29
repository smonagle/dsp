[Think Stats Chapter 8 Exercise 3](http://greenteapress.com/thinkstats2/html/thinkstats2009.html#toc77)

---

<pre>
def GameSimulator(lam = 2, m=1000):
    lam_estimates = []
    for i in range(m):
        L = SimulateGame(lam)
        lam_estimates.append(L)
    
    print('rmse L', RMSE(lam_estimates, lam))
    print('mean error L', MeanError(lam_estimates, lam))

GameSimulator()
</pre>
**Output:  
rmse L 1.4064138793399332  
mean error L 0.038
---
