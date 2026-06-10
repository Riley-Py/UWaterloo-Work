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
*Expected Value (Discrete)*: $$ E[X] = \sum x P(X = x)$$
*Expected Value (Continuous)*: $$ E[X] = \int_{-\infty}^\infty xf(x) {dx}$$
*Expected Value Function (Discrete)*: $$E[g(X)] = \sum_x g(x) P(X=x)$$
*Expected Value Function (Continuous)*: $$ E[g(X)] = \int_{-\infty}^\infty g(x)f(x){dx}$$
*Variance of Expected Value*: $$ \sigma^2 = E[(X - \mu)^2]$$
*Variance of Expected Value (alt.)*: $$ \sigma^2 = E(X^2) - \mu^2$$
*Variance of Expected Value Function*: $$\sigma_{g(X)}^2 = E[(g(X) - \mu_{g(X)})^2]$$
*Chebyshev's Theorem*: $$ P(|X - \mu| \ge k\sigma) \le {1 \over k^2}$$
*Discrete Uniform Distribution*: $$ f(x_i) = {1\over n}$$
*Discrete Uniform Distribution Mean (consecutive values)*: $$ E[X] = {{{first} + {last} \over 2}}$$
*Discrete Uniform Distribution Variance (consecutive values)*: $$ (n ^2 - 1) \over 12 $$
*Binomial Distribution*: $$ b(x;n,p) = \binom{n}{x}p^x(1 - p)^{n-x}$$
*Binomial Distribution (Mean)*: $$ np$$
*Binomial Distribution (Variance)*: $$np(1-p)$$
*Multinomial Distribution*: $$ P(X_1 = x_1, \cdots, X_k = x_k) = {n! \over {x_1!x_2!\cdots x_k!}}p_1^{x_1} p_2^{x_2} \cdots p_k^{x_k}$$
*Hypergeometric Distribution*: $$P(X=x) = {{\binom{K}{x} \binom{N - K}{n-x}}\over \binom{N}{n}}$$
*Hypergeometric Distribution (Mean)*: $$nk \over N$$
*Hypergeometric Distribution (Variance)*: $${{N - n}\over N-1}n {k \over n} \left(1 - {k \over N} \right)$$
*Multivariate Hypergeometric Distribution*: $$ P(X_1 = x_1, \cdots, X_k = x_k) = {{{\binom{N_1}{x_1}}{\binom {N_2}{x_2}}\cdots {\binom{N_k}{x_k}}}\over \binom{N}{n}}$$
*Negative Binomial Distribution*: $$ b^*(x; k, p) = {{\binom{x - 1}{k - 1}}p^k(1 - p)^{x-k}}, x=k, k+1, k+2, \dots$$
*Negative Binomial Distribution (Mean)*: $$ k \over p$$
*Negative Binomial Distribution (Variance)*: $$ {k (1 - p)} \over p^2$$
*Geometric Distribution*: $$g(x; p) = pq^{x - 1}, x = 1,2,3\dots$$
*Geometric Distribution (Mean)*: $$ 1 \over p$$
*Geometric Distribution (Variance)*: $$ {1 - p} \over p^2$$
*Poisson Distribution*: $$p(x; \lambda t) = {{e^{-\lambda t} (\lambda t)^x}\over x!}, x=0,1,2\dots$$
*Poisson *







