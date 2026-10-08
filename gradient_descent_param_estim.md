PGB
2026-10-08

When you estimate parameters in linear regression, you are trying to
find the value that, when used in conjunction with the independent
variables, returns a line that best represents the data that you are
working with. The so-called “line of best fit”. There are several ways
to estimate the value of the parameters that define that line. The
simplest (and most frequently taught) is to draw a straight line through
the data, and then “rotate” it until the difference between the observed
data and the line, with respect to the y axis, is minimised. This is
usually quantified by squaring this vertical distance and squaring it
(to account for negative values). In essence, this “rotation” of the
line is equivalent to trying out a number of parameters, and then
minimising the sum of squares, which tells us the quality of the fit.
The smallest value for the sum of squares is expected to return the best
estimates for the parameters that explain the data. You can see a manual
calculation for this value using an analytical approach in my [ordinary
least
squares](https://github.com/PlantsGenesBugs/OLS_parameter_estimation)
repo, and an alternative way for parameter optimisation in my [maximum
likelihood
estimation](https://github.com/PlantsGenesBugs/Max_Likelihood_Estimation)
repo.

In this file I will be using a fourth method called **gradient
descent**. Gradient descent is a method that aims to find the “line of
best fit” by minimising a value that assesses the quality of that fit
(somewhat like finding the smallest sum of squares). The value we will
be using is the mean square error, and in this context it is also called
the cost function. This is the value we want to optimise. Mean square
error is essentially the residual sum of squares divided by 2n:

$$
\frac{1}{2n}(y - X\beta)^T(y - X\beta)
$$
