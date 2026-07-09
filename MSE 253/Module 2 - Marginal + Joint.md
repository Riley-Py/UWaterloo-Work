## Joint Probability Distribution
- Simultaneous outcomes of more than one variable, like so: $F(x,y) = P(X = x, Y = y)$ 

### Joint Probability Mass Function
- Properties of joint probability mass function for discrete variables:
	1. $f(x,y) \geq 0$ for all $(x,y)$
	2. $\sum_x \sum_y f(x,y) = 1$
	3. $P(X = x, Y = y) = f(x,y)$
### Joint Probability Density Function
- Properties of joint probability density function for continuous variables:
	1. $f(x,y) \geq 0$ for all $(x,y)$
	2. $\int_{-\infty}^\infty \int_{-\infty}^\infty f(x,y){dx}{dy} = 1$
	3. $P((X,Y) \in R) = \int \int_R f(x,y){dx}{dy}$ 

## Marginal Distribution
- Tells about one variable by itself without the other variable

### Discrete Random Variables
- For $x$, $P(X = x) = \sum_y P(X= x, Y = y)$ 
- For $y$, $P(Y = y) = \sum_x P(X = x, Y = y)$

### Continuous Random Variables
- For $x$, $P(X = x) = \int_{-\infty}^\infty f(x,y){dy}$
- For $y$, $P(Y = y) = \int_{-\infty}^\infty f(x,y) {dx}$

#mse253 
#module2 