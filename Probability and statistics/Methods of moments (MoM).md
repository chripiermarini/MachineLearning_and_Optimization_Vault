Tags:

- #Parametric-inference

The method of moments is one of the most intuitive and easiest techniques to estimate the parameter of a sample distribution. 

The main idea comes from the Law of Large numbers, for which we have that sample average converges to the actual average of the sample distribution.

The method works as follow:

1) First, for each parameter we want to estimate, we compute the *theoretical j-th moment* $\mathbb{E}[x^j]$
2) Then, we compute the *sample j-th moment* $\frac{1}{n}\sum_i^n{x^j_i}$ ;
3) We assume they are equal and hence we compute the estimates solving the linear system *theoretical = sample*.

###### Example
If we had a *Normal distribution X ~ $N(\mu, \sigma^{2})$*, we could compute the two parameters of :4
the distribution using the MoM estimator using the first and second moments. In theory, we know that

$$
\mu = \mathbb{E}(X) \\
\sigma^2 + \mu^2 = \mathbb{E}(X^2)
$$
Then, for the MoM estimator, we can compute the parameter by solving the linear system of equation

$$
\left\{
\begin{aligned}
\mu = \frac{1}{n} \sum_{i= 1}^{N}X_i \\
\sigma^2 + \mu^2 = \frac{1}{n} \sum_{i= 1}^{N}X_i^{2} 
\end{aligned}
\right.
$$
3 important properties to remember for the MoM estimator. Let's assume that $\hat{\theta}$ is the MoM estimator. Under appropriate conditions on the model, we may state the following: 

1) $\theta$ exists with probability tending to 1
2) The estimate is consistent: $\hat{\theta}_n \rightarrow \theta$ ([[Convergence in probability]]) 
3) The estimate is asymptotically Normal:
$$
\sqrt{n}(\hat{\theta}_n - \theta) \xrightarrow{d} \mathcal{N}(0, \Sigma)
$$
where
$$
\Sigma = g \, \mathbb{E}_\theta(Y Y^T) g^T,
$$
$Y = (X, X^2, \dots, X^k)^T$, $g = (g_1, \dots, g_k)$ and $g_j = \frac{\partial \alpha_j^{-1}(\theta)}{\partial \theta}$.

