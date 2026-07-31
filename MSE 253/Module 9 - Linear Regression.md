
## Simple Linear Regression
- Must be a random component added to equation that relates variables
- Variables:
	- $x$ - independent variable, regressor
	- $y$ - dependent variable, response
	- $\beta_0$ - intercept
	- $\beta_1$ - slope
	- $\epsilon$ - error, disturbance
- *Homogenous variance assumption* - variances of population being compared are equal across groups
	- Based on assumption: $E(\epsilon) = 0$ and ${Var(\epsilon)} = \sigma^2$ 
- *True Regression Model* - like SLR formula, but using the population attributes instead of sample attributes
- *Fitted regression* - predicted line of true regression; $\hat{y}$ is the notation
- *Residual* - error in the fitted regression when compared to the true regression
	- Computed with $e_i = y_i - \hat{y_i}$ 
	- Small values are sign of good fit

### Least Squares
- Allows for the estimation of the true linear regression line
- Notation
	- $S_{xx} = \sum_{i = 1}^n (x_i - \bar{x})^2$ 
	- $S_{yy} = \sum_{i = 1}^n (y_i - \bar{y})^2$ 
	- $S_{xy} = \sum_{i = 1}^n(x_i - \bar{x})(y_i - \bar{y})$ 
	- $b_1 = {S_{xy} \over S_{xx}}$
	- $b_0 = \bar{y} - b_1\bar{x}$ 
- Assume that $\beta_0$ and $\beta_1$ are normally distributed
- For $\beta_1$
	- *Mean:* $\beta_1$
	- *Variance*: $\sigma^2 \over \sum_{i = 1}^n (x_i - \bar{x})^2$ 
	- *Standard Error*: $s \over {\sqrt{\sum(x_i  - \bar{x})^2}}$ 
- For $\beta_0$
	- *Mean*: $\beta_0$
	- *Variance*: $\sigma^2 ({1 \over n} + {\bar{x}^2 \over \sum_{i=1}^n(x_i - \bar{x})^2})$ 
	- *Standard Error*: $s \sqrt{{1 \over n} + {\bar{x}^2 \over \sum(x_i - \bar{x})^2}}$ 
- To estimate variance: $s^2 = {\sum_{i = 1}^n (y_i - \hat{y_i})^2 \over {n - 2}}$ 
- 