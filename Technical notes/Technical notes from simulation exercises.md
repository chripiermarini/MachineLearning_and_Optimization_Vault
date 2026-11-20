##### Simulation

When performing Discrete Event Simulation, the sequence of event that must be performed is the following.

First, we need to understand what is the probability distribution that best describes the underlying process. This can be done by the means of multiple tools: 
	- *Kolmogorov-Smirnov tests*, which are used to compare the empirical cumulative distribution function with the theoretical distribution function that we are assuming to be true. It computes the vertical distance between the two distributions.
	- *Q-Q plot*: quantile-quantile plots, where we plot the observed quantile we obtained with the ones we are expecting, drawn from the same distribution. If they are coming from the same distribution, it means that our hypothesis is correct, we should see all the blue points along the diagonal of the positive square.
	- *Testing the properties of specific distributions*: i.e. hazard rate per memorylessness of the exponential distribution.

***Important note***: in practice, we would never find a first good distribution on the first try. Usually, we either have to segment the distribution based on specific features (peak/off-peak, hourly level, origin, etc.).

Another good practice would be to apply fitting on multiple distributions at the same time, while also using AIC/BIC based comparisons. Generally speaking, we both want ot use the AIC value (the smaller, the better, as it gives more importance to simpler models) and the KS p-value. The smaller the p-value, the higher the evidence against the null hypothesis that the empirical distribution follows the theoretical distribution.

TODO: small refresher on Gamma, Exponential, Weibull and Normal/Gaussian distribution.

[[SimPy]]
