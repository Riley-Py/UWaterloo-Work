- *Point estimation* - single value as an estimate of a population parameter, without any information about accuracy of estimation
- *Interval estimation* - interval that contains true value of parameters with some probability

### Confidence Intervals
- $\theta_L$ and $\theta_U$ are *confidence limits*
- $1 - \alpha$  is *confidence level*
- $\theta_L < \theta < \theta_U$ is called *confidence interval*
- For more, see [[Formulas|formulas]] 
- There will be errors; again, see formulas
- If $\sigma$ is unknown, there are two options:
	1. *Large-Sample Confidence Interval* - $n \ge 30$ 
		- Use sample $s$ as substitute
	2. *Random Sample is from Normal Distribution* - $n \le 30$
		- Use T-distribution
### Difference Between Two Sample Means
- Independent populations
- Normal populations
- See formulas for equation

### Point Estimator of Proportion
- Use the p-statistic
- For confidence interval, use the Z-distribution/CLT

### Notes about P
- $n\hat{p} \ge 5$ and $n\hat{q} \geq 5$ 
- When $n$ is small and $p$ is close to 0 or 1, confidence interval is bad
- Sample size should be following:
	- $n = {z_{\sigma \over 2}^2pq \over e^2}$ 
- To estimate $n$ without knowing $p$, use this
	- $n = {z_{\sigma \over 2}^2 \over 4e^2}$ 
### Difference Between Two Binomial Parameters 
- Independent random samples
- Two binomial populations
- $\hat{p_i} = {x_i \over n_i}$ 
- See formulas

### Confidence Interval for $\sigma^2$ and $\sigma_1^2 \over \sigma_2^2$: 
- See formulas

### Maximum Likelihood Estimation (MLE)
- Chooses explanation that would produce evidence that is found - the observed data
- 
- Example: Bernoulli Distribution with dataset ${1, 1, 0, 1, 1}$ 
	1. Write the likelihood function: $$L(\theta) = f(x_1; \theta) \times f(x_2; \theta) \times \cdots f(x_i; \theta)$$
		- $f(x_i; \theta)$ is the PDF of a particular discrete distribution
	2. Take the log of it: $$l(\theta) = {ln}L(\theta) $$
	3. Differentiate
	4. Set derivative to 0
	5. Solve for $\theta$ 
#mse253 
#module7 
