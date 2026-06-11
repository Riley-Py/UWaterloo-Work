### Uniform Distribution
- Most basic of continuous 
- Happens over fixed interval $[a,b]$ 

### Normal (Gaussian) Distribution
- Most used distribution in statistics
- Shows up naturally in theory and the real-world
- Mathematically convenient - only two variables
- The distribution that graphs is called a *Normal Curve*
	- Bell-shaped
	- Mean and variance
#### Normal Curve
- Mean, median, and mode at $x = \mu$ 
- Symmetric around mean
- Approaches horizontal axis in the left and right direction of $x$ 

#### Mean and Variance of Normal Distribution
- $\mu$ determines center along horizontal axis
- $\sigma$ determines spread of data and peak height of the normal curve

#### Properties of Normal Distribution
- $P (\mu - \sigma < X < \mu + \sigma) = 0.6827$
- $P (\mu - 2\sigma < X < \mu + 2\sigma) = 0.9545$
- $P (\mu - 3\sigma < X < \mu + 3\sigma) = 0.9973$
- *Six-Sigma*: width of normal distribution

### Standard Normal Distribution
- Normal distribution with $\mu = 0$ and $\sigma^2 = 1$ 
- Denoted with $Z$ 
- Common reference scale for all normal distributions

#### Approximating Binomial with Normal
- Use when:
	- $np \geq 5$ 
	- $n(1 - p) \geq 5$ 
- Where:
	- $\mu = np$ 
	- $\sigma^2 = np (1 - p)$
- *Continuity correction* is required, as a discrete distribution is being approximated by a continuous distribution
	- Must add $+0.5$ 
### Exponential Distribution
- Waiting time between random events that happen at a constant rate
	- Similar to Poisson distribution ([[Module 3 - Expected Value + Discrete Distributions|see module 3]])
	- $\beta = {1 \over \lambda}$, where:
		- $\beta$ - scale parameter (average waiting time)
		- $\lambda$ - how long you wait on average
### Gamma Distribution
- Like exponential distribution, and similar to negative binomial distribution, where we are waiting until multiple poisson events occur
	- Extended version of exponential, with multiple events
#### Properties of Gamma Function
- Gamma function: $\Gamma (n) = {\int_0^\infty t^{n - 1}e^{-t} {dt}}$ 
1. $\Gamma (n) = (n-1)(n-2)\dots$ 
2. $\Gamma (n) = (n - 1)!$ 
3. $\Gamma (1) = 1$
4. $\Gamma ({1 \over 2}) = \sqrt(\pi)$ 

#### Gamma Distribution
- Models waiting time until multiple random events occur

### Memoryless Property
- Only applies to exponential distribution and the geometric distribution
- Past doesn't matter; only care about the present
- General form: $$P(X > t_0 + t | X > t_0) = P(X > t)$$
### Incomplete Gamma Function
- Used when you want the gamma function up until a certain point
- Incomplete Gamma function formula: $\gamma(\alpha, x) = \int_0^x t^{\alpha - 1}e^{-t}{dt}$ 
- Table will be provided with values

### Chi-Squared Distribution
- Another subset of the gamma distribution
- Used for confidence intervals for variance and standard deviation


