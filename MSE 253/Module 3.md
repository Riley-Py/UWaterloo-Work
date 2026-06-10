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
### Multinomial Experiment
- Each trial having more than two possible outcomes

#### Multinomial Distribution
- Distribution that represents more than two outcomes - an extension of the binomial distribution, where: 
	- $p_1, p_2, \cdots, p_k$ are successes
	- $x_1, x_2, \cdots, x_k$ are the outcomes
	- $n$ are the amount of trials
	- $\sum_{i=1}^k x_i = n$ 
	- $\sum_{i=1}^k p_i = 1$ 
### Hypergeometric Distribution
- Similar to binomial distribution, as we are interested in finding number of observations that fall into a particular category
- Doesn't require independence and is based on sampling without replacement
- Variables for distribution:
	- $N$ - population size
	- $K$ - number of successes in population
	- $n$ - sample size
	- $x$ - number of successes in sample
#### Multivariate Hypergeometric Distribution
- Like hypergeometric distribution, with more categories
- Similar variables to hypergeometric/binomial distribution
#### Relation to Binomial
- If ${n\over N} \leq 0.05$, binomial can be used to approximate hypergeometric distribution
- In that case:
	- $p = {k \over N}$
	- $\mu = np = {nk \over N}$ 
	- $\mu^2 = np (1 - p) = n{k \over N}\left (1 - {k \over N}\right)$ 
### Negative Binomial Experiment
- Trials are repeated until a fixed number of successes
- Interested in the probability that the $k^{th}$ success occurs on the $x^{th}$ trial

#### Negative Binomial Distribution
- Counts how may trials are needed to get a certain number of successes

#### Geometric Distribution
- Special case of negative binomial
	- Number of trials until first success occurs

### Poisson Experiment
- Counting how many times an event occurs in a fixed interval of time, space, etc.
	- Examples: Number of calls received per hour, number of field mice per acre

#### Poisson Process
- Conditions for Poisson to be valid:
	1. Number of outcomes in time interval or specified region is independent of number that occurs in any other time interval/region - no memory
	2. Probability of single will occur during short time interval/small region is proportional to length of time interval/size of region - doesn't depend on number of outcomes 