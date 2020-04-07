# Least-squares fitting

A very common measure of how well a given curve fits a set of data points is by calculating the sum of the squares of the residuals, i.e. for n data points we have:

![](images/eqn-sum-squares-1.svg)

Equivalently this can be written as ![](images/eqn-sum-squares-2.svg).

According to this metric, the lower the sum, the better your curve fits the data points.  If you calculate this sum for the two models in the example we have been looking at, you get ≈4.8 for model 1 and ≈1.1 for model 2, which suggests that model 2 is a better fit, which agrees with our intuition.

## Line of best fit

If we want to find the curve that best fits the data, according to the least-squares metric, then we want to find the one which gives the **minimum** value of *S* .  If we expect a linear relationship then we can write the predicted values at the observation points as *f(x<sub>i</sub>) = mx<sub>i</sub> + c*.  Plugging this into our equation for *S* gives:

![](images/eqn-sum-squares-3.svg)

The objective now is to find the values of *m* and *c* for which *S* is the smallest (recall that x<sub>i</sub> and y<sub>i</sub> are our data points and therefore cannot be varied).  *S* can be minimized using calculus, which gives the following solution for the best fitting line:

![](images/eqn-best-fit-m.svg)

![](images/eqn-best-fit-c.svg)

where ![](images/eqn-xbar.svg) and ![](images/eqn-ybar.svg) are the mean values of *x* and *y*, respectively.


