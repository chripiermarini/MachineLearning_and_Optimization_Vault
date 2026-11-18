Tags:
- #Parametric-inference 

Maximum Likelihood Estimation (MLE) is one of the most widely used techniques to estimate model parameters. It function as follows:

Let $X_1, \dots, X_n$ IID with *pdf* function $f(x;\theta)$. The MLE estimation method requires to compute the parameters $\theta$ that maximises the *likelihood function*:

$$
L_n(\theta) = \prod_{i=1}^{n}f(x_i; \theta)
$$
The likelihood function is the joint density of the data, expect we treat it as a function of the parameter $\theta$.

Hence, $\hat{\theta}_{MLE} = \max_{\theta} L_n(\theta)$.  

The overall idea is to compute the parameter of the parametric function such that the model fits the available data the most.

###### Examples

- For the Normal gaussian model $N(\mu, \sigma^2)$ , the $\mu_{MLE} = \bar{X}_n$ and the $\sigma^2_{MLE} = S^2$  
- For the Bernouilli distribution, $\mu = \sum_{i=1}^nX_i/n$ 

Please check 