- *Hypothesis* - statement about parameters of one or more populations; truth/false isn't known with hypothesis
- *Null Hypothesis* - hypothesis that's tested $H_0$ 
- *Alternative Hypothesis* - rejection of $H_0$
- One of two conclusions
	- *Reject $H_0$ in favour of $H_1$*
	- *Fail to reject $H_0$*
	- Note: no accepting either hypothesis
- *Two-Sided* - $H_1$ is on both sides of statistic
- *One-Sided* $H_1$ is only one side of statistic
- *Critical region* - region where $H-)$ would be rejected
	- *Critical values* - last numbers passing into critical region
	- Diagram:
		- ![[Pasted image 20260731083237.png]]
### Errors
- *Type 1* - rejection of null hypothesis when it's true
- *Type 2* - failing to reject null hypothesis when it's false
- Diagram
	- ![[Pasted image 20260731083354.png]]
- *Significance Level* - probability of type 1
	- Example: $\alpha = P(\bar{x} < 0.172 \space {or} \space \bar{x} > 0.228 | \mu = 0.2)$
- *Beta Value* - probability of type 2
	- Example: $\beta = P(0.172 \leq \bar{x} \leq 0.228 | \mu = 0.4)$ 
- *Power of a Test* - probability of rejecting $H_0$ given that alternative is true
	- Computed as $1 - \beta$ 

### Procedures for Testing

#### Fixed Significance Level
1. State null/alternative hypothesis
2. Choose fixed significance level
3. Choose appropriate test statistic and establish critical region based on $\alpha$ 
4. Reject $H_0$ if computed test statistic is in critical region; don't reject otherwise
5. Conclusions

#### P-Value
1. State null/alternative hypothesis
2. Choose test statistic
3. Compute $P$ value based on computed value of test statistic
4. Use judgement based on $P$ value to draw conclusions
	- If $P \leq \alpha$ reject $H_0$
	- If $P > \alpha$, fail to reject $H_0$ 

#### Proportional Testing - Small Samples
1. $H_0: p = p_0$ 
2. Choose $H_1$
3. Choose level of significance equal to $\alpha$
4. Test statistic is binomial variable $X$ with $p = p_0$
5. Compute $p$ value
6. Draw conclusions

#### Proportional Testing - Large Samples
1. $H_0: p = p_0$ 
2. Choose $H_1$
3. Choose level of significance equal to $\alpha$
4. Use normal approximations where $\mu = np_0$ and $\sigma^2 = np_0q_0$ 
5. Compute $p$ value
6. Draw conclusions

#### Two Populations
- Do the same as above, but now calculate $\hat{p} = {{x_1 + x_2} \over {n_1 + n_2}}$ and $z



- Look at [[Module 6 - Sampling|module 6]] and [[Module 7 - Estimation|module 7]] for more info; look at [[Formulas|formulas]] for the associated equations

#mse253 
#module8 
