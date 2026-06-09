## Measure of Location
- *Mean* - sum of all values divided by number of values
- *Median* - Middle value in ordered data
	- If even, average the two middle values
- *Mode* - most frequent value
	- There can be more than one
- *Percentile* - value below which a % of data fall
- *Quartiles* - divide data into 4 equal parts
	- Q1 (25%), Q2 (50%), Q3 (75%)
## Variability
- *Range* - difference between largest and smallest value
- *Mean Absolute Deviation* - average distance of data from mean
- *Variance* - average of squared deviations form the mean
- *Standard Deviation* - square root of variance (in same unit as data)

## Probability
- Chance that outcome occurs
- For event, it's the sum of outcomes that comprise said event

## Conditional Probability
- Chance of event B happening with the knowledge of A
- Used when additional info becomes available

## Independence
- Knowledge of outcome of the experiment is in event A does not affect the probability that the outcome is in event B

## Total Probability Theorem
- A way to find probability of an event by breaking it into different cases

## Bayes' Rule
- Updating probability when you learn new information
- Start with what you believed before, then adjust belief using new evidence

## Discrete VS. Continuous
- *Discrete* - countable outcomes
	- Example: months of the year, or a sequence of whole numbers
- *Continuous* - uncountable outcomes
	- Example: temperature, or weight
## Random Variables
- Associate number with each outcome in sample space
- Since outcome of experiment is not known in advance, resulting value of random variable is not known in advance
### Discrete
- Countable range
- Represents counts
### Continuous
- Uncountable range
- Measured data

## Probability Distribution
- Description of probabilities with all possible values of random variable

### Probability Mass Function (PMF)
- Used for discrete random variables
- Has these three properties:
	1. $f(x_i) \geq 0$ 
	2. $\sum_{i=1}^n f(x_i) = 1$
	3. $f(x_i) = P(X = x_i)$
### Probability Density Function (PDF)
- Used for continuous random variables, as $P (X = x) = 0$ for all values of $x$
- Calculated over an interval
	- Doesn't matter if interval is closed/open
- Has these properties:
	1. $f(x) \geq 0$ 
	2. $\int_{-\infty}^\infty f(x) {dx} = 1$ 
	3. $P(a \leq X \leq b) = \int_a^b f(x)dx$ 
		- Area under $f(x)$ from $a$ to $b$
## Cumulative Probability
- Random variable is less than or equal to a certain value

### Cumulative Distribution Function (CDF) (Discrete)
- Has these three properties:
	1. $F(x) = P(X \leq x_i)$
	2. $0 \leq F(x) \leq 1$ 
	3. If $x \leq y$, then $F(x) \leq F(y)$ 

### Cumulative Distribution Function (CDF) (Continuous)
- Has this property for $-\infty < x < \infty$: $$ F(x) = P(X \leq x) = \int_{-\infty}^x f(u) {du}$$
#mse253
#module1 
