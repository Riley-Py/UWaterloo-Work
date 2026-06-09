## Expected Value (Mean)
- Average value you expect in long run if you repeat a random experiment many times

## Expected Value (Function)
- Average output of the function in the long run instead of value

## Notes on Mean
- Describes where probability distribution is centered
- Doesn't describe shape of distribution

## Variance
- *Variability* - how spread out values are from expected value
- Measure of variability

## Linear Combinations of Random Variables
- If $a$ and $b$ are constant, these are true:
	1. $E(aX + b) = aE(X) + b$
	2. $E(b) = b$
	3. $E(aX) = aE(X)$
	4. $E[g(X)\pm h(X)]=E[g(X)] \pm E[h(X)]$
## Chebyshev's Theorem
- No matter what the distribution looks like, most of the data must be within a few standard deviations of the mean
- The probability that any random variable $X$ will deviate by more than $k$ standard deviations of the mean is at most $1 \over k^2$

## Discrete Probability Distributions

### Discrete Uniform Distribution
- Simplest distribution
- Each possible value is equally likely
- Finite possible values

### Bernoulli Trial/Process
- Repeated trials of same experiment
- Has only two possible outcomes (binary)
- Probability of success/failure is constant across trials
- Repeated trials are independent
#### Binomial Random Variable
- Represents number of successes within a Bernoulli trial
#### Binomial Distribution
- Distribution that represents the Bernoulli trial, where:
	- $p$ is success probability
	- $1 - p$ is failure probability
	- $x$ is number of successes
	- $n - x$ is number of failures
- Since trials are independent, multiply all probabilities corresponding to different outcomes