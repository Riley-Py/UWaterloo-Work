*Mean*: $$\sum x_i \over n$$
*Range*: $${max}(x) - {min}(x) $$
*Mean Absolute Deviation (MAD)*: $$ {1 \over n} \sum_{i=1}^n |x_i - \bar{x}|
$$
*Variance*: $${1\over n}\sum_{i=1}^n (x_i - \bar {x})^2 $$
*Standard Deviation*: $$\sigma = \sqrt {{1 \over n} \sum_{i=1}^n (x_i - \bar{x})^2} $$
*Conditional Probability*: $$ P(A|B) = {P(A \cap B)\over P(B)} $$
*Conditional Probability (alt.)* $$ P(A \cap B) = P(A|B)P(B), P(B) > 0$$
*Independence*: $$ P(A \cap B) = P(A)P(B) $$
*Total Probability Theorem* $$ P(A) = \sum_{i=1}^n P(A | B_i) P(B_i)$$
*Total Probability Theorem (Two Events)*: $$P(A) = P(A|B)P(B) + P(A|B^c)P(B^c)$$
*Bayes' Rule*: $$P(A|B) = {{P(B|A)P(A)} \over P(B)} $$
*Mutual Exclusion*: $$ P(A \cup B) = P(A) + P(B), A \cap B = \emptyset$$
### Expected Value
*Expected Value (Discrete)*: $$ E[X] = \sum x P(X = x)$$
*Expected Value (Continuous)*: $$ E[X] = \int_{-\infty}^\infty xf(x) {dx}$$
*Expected Value Function (Discrete)*: $$E[g(X)] = \sum_x g(x) P(X=x)$$
*Expected Value Function (Continuous)*: $$ E[g(X)] = \int_{-\infty}^\infty g(x)f(x){dx}$$
*Variance of Expected Value*: $$ \sigma^2 = E[(X - \mu)^2]$$
*Variance of Expected Value (alt.)*: $$ \sigma^2 = E(X^2) - \mu^2$$
*Variance of Expected Value Function*: $$\sigma_{g(X)}^2 = E[(g(X) - \mu_{g(X)})^2]$$
### Chebyshev
*Chebyshev's Theorem*: $$ P(|X - \mu| \ge k\sigma) \le {1 \over k^2}$$
## Discrete Distributions
### Uniform
*Discrete Uniform Distribution*: $$ f(x_i) = {1\over n}$$
*Discrete Uniform Distribution Mean (consecutive values)*: $$ E[X] = {{{first} + {last} \over 2}}$$
*Discrete Uniform Distribution Variance (consecutive values)*: $$ (n ^2 - 1) \over 12 $$
### Binomial
*Binomial Distribution*: $$ b(x;n,p) = \binom{n}{x}p^x(1 - p)^{n-x}$$
*Binomial Distribution (Mean)*: $$ np$$
*Binomial Distribution (Variance)*: $$np(1-p)$$
*Multinomial Distribution*: $$ P(X_1 = x_1, \cdots, X_k = x_k) = {n! \over {x_1!x_2!\cdots x_k!}}p_1^{x_1} p_2^{x_2} \cdots p_k^{x_k}$$
### Hypergeometric
*Hypergeometric Distribution*: $$P(X=x) = {{\binom{K}{x} \binom{N - K}{n-x}}\over \binom{N}{n}}$$
*Hypergeometric Distribution (Mean)*: $$nk \over N$$
*Hypergeometric Distribution (Variance)*: $${{N - n}\over N-1}n {k \over n} \left(1 - {k \over N} \right)$$
*Multivariate Hypergeometric Distribution*: $$ P(X_1 = x_1, \cdots, X_k = x_k) = {{{\binom{N_1}{x_1}}{\binom {N_2}{x_2}}\cdots {\binom{N_k}{x_k}}}\over \binom{N}{n}}$$
### Negative Binomial
*Negative Binomial Distribution*: $$ b^*(x; k, p) = {{\binom{x - 1}{k - 1}}p^k(1 - p)^{x-k}}, x=k, k+1, k+2, \dots$$
*Negative Binomial Distribution (Mean)*: $$ k \over p$$
*Negative Binomial Distribution (Variance)*: $$ {k (1 - p)} \over p^2$$
### Geometric
*Geometric Distribution*: $$g(x; p) = pq^{x - 1}, x = 1,2,3\dots$$
*Geometric Distribution (Mean)*: $$ 1 \over p$$
*Geometric Distribution (Variance)*: $$ {1 - p} \over p^2$$
### Poisson 
*Poisson Distribution*: $$p(x; \lambda t) = {{e^{-\lambda t} (\lambda t)^x}\over x!}, x=0,1,2\dots$$
*Poisson Distribution (Mean and Variance)*: $$ \mu = \sigma^2 = \lambda t$$
## Continuous Distributions
### Uniform
*Uniform Distribution*: $$\begin{numcases} {f(x; a, b) = } {1 \over b - a} & $a \leq x \leq b$ \\ 0, & otherwise \end{numcases}$$
*Uniform Distribution (Mean)*: $$ {a + b}\over 2$$
*Uniform Distribution (Variance)*: $$ {(b - a)^2} \over 12$$
### Normal
*Normal Distribution (PDF)*: $$ n(x; \mu, \sigma) = {1 \over {\sqrt{2 \pi \sigma}}}e^{-{1 \over 2 \sigma^2}(x - \mu)^2}, -\infty < x < \infty$$
*Normal Distribution (Mean)*: $$ \mu$$
*Normal Distribution (Variance)*:  $$ \sigma^2$$
### Standard Normal
*Conversion Between Normal and Standard Normal*: $$Z = {{X - \mu}\over \sigma}$$ $$ P(X \leq x) = P \left({{X - \mu}\over \sigma}\leq {{x - \mu}\over \sigma}\right) = P(Z \leq z)$$
$$ P(Z > z) = 1 - P(Z < z)$$

### Exponential Distribution
*Exponential Distribution (Rate Form $\lambda$ )*: $$\lambda e ^{-\lambda x}$$
*Exponential Distribution (Scale Form $\beta$ )*: $${1 \over \beta}e^{-x \over \beta}$$
*Relationship between $\lambda$ and $\beta$*: $$ \beta = {1 \over \lambda}, \space \lambda = {1 \over \beta}$$
*Exponential Distribution (Mean)*: $$ \beta \space {or} {1 \over \lambda}$$
*Exponential Distribution (Variance)*: $$ \beta^2 {or} {1 \over \lambda^2}$$
### Gamma Distribution

*Gamma Distribution (Scale Form $\beta$)*: $$ f(x; \alpha, \beta) = {{1 \over \beta^\alpha \Gamma(\alpha)}x^{\alpha - 1}e^{{-x \over \beta}}}$$
*Gamma Distribution (Mean)*: $$ \alpha \beta$$
*Gamma Distribution (Variance)*: $$\alpha \beta^2$$
*Relationship between Gamma and Exponential Distribution*: $$X \sim {Exp}(\lambda) = X \sim {Gamma} (1, \lambda)$$
### Chi-Squared Distribution

*Chi-Squared Distribution*: $$ f(x; v) = {1 \over {2^{v \over 2}\Gamma ({v \over 2})}} x^{{v \over 2} - 1}e^{-x \over 2}$$
*Chi-Squared Distribution (Mean)*: $$\mu = v$$
*Chi-Squared Distribution (Variance)*: $$ \sigma^2 = 2v$$
### Beta Distribution

*Beta Distribution*: $$f(x; \alpha, \beta) = {1 \over B(\alpha, \beta)}x^{\alpha - 1}(1 - x)^{\beta - 1}$$
*Beta Distribution (Mean)*: $${\alpha \over {\alpha + \beta}}$$
*Beta Distribution (Variance)*: $$ {\alpha \beta} \over {(\alpha + \beta)^2}{(\alpha + \beta + 1)}$$
### Lognormal Distribution

*Lognormal Distribution*: $$f(x; \mu, \sigma) = {1 \over {x\sigma\sqrt{2\pi}}} * e^{-{(lnx - \mu)^2 \over 2\sigma^2}}$$
*Lognormal Distribution (mean)*: $$ e^{\mu + {\sigma^2 \over 2}}$$
*Lognormal Distribution (variance)*: $$e^{2\mu + \sigma^2}(e^{\sigma^2 - 1})$$

### t-Distribution

*t-Statistic*: $$t = {{\bar x - \mu} \over {s \over \sqrt n}} $$
*Degrees of Freedom*: $${df} = n - 1 $$


### Moments

*Discrete nth-Moment*
$$E(X^r) = {\sum_x x^rp(x)}$$
 *Continuous nth-Moment*
$$E(X^r) = {\int_{a}^{b}x^rf(x){dx}}$$
 *Moment Generating Function - Discrete*
$$E(e^{tX}) = {\sum_x}e^{tx}p(x)$$
*Moment Generating Function - Continuous*
$$E(e^{tX}) = {\int_a^b e^{tx}f(x)dx}$$
*Conversion Between Function and Moment*
$$E(X^r) = {{d^rE(e^{tX})} \over {dt}^r}$$
Note: r represents the amount of times to take derivative (first derivative, second, etc.)

### Sampling

*Variance*: $$S^2 = {{1 \over n - 1} \sum_{i =1}^n (X_i - \bar X)^2} $$
*Standard Deviation*: $$ S = \sqrt{S^2}$$
*Central Limit Theorem*: $$Z = {{\bar X - \mu \over {\sigma \over \sqrt n}}} $$
*Difference Between Sample Means (Mean)*: $$ \mu_{{\bar X_1 - \bar X_2}} = \mu_1 - \mu_2$$
*Difference Between Sample Means (Variance)*: $$\sigma_{\bar X_1 - \bar X_2}^2 = {\sigma_1^2 \over n_1} + {\sigma_2^2 \over n_2}$$
*Difference Between Sample Means (Z-statistic)*: $$Z = {(\bar X_1 - \bar X_2) - (\mu_1 - \mu_2)\over {\sqrt {{\sigma_1^2 \over n_1} + {\sigma_2^2 \over n_2}}}}$$
*Chi-Squared Statistic*: $$\chi^2 = {(n - 1)S^2 \over \sigma^2} $$
*Chi *














