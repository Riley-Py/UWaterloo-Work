- *One-One Transformations* - each value $x$ is related to one value $y = u(x)$ and that each value $y$ is related to one value $x = w(y)$,obtained by solving $y = u(x)$ for $x$ in terms of $y$ 
- More details can be found in the slides

## Moments
- Used to characterize distribution/shape of random variables (*Moment*)
- Different moments give different information
	- *First moment* - expected value
	- *Second moment*  - variance
- Properties of moment generating function:
	- If $M_X(t) = M_Y(t)$, then $X$ and $Y$ have the same probability distribution
	- $M_{X + a}(t) = e^{at} M_X(t)$
	- $M_{aX}(t) = M_X({at})$
	- If $Y = X_1 + X_2 + \cdots + X_n$, then $M_Y(t) = M_{X1}(t) \times M_{X2}(t) \times \cdots M_{Xn}(t)$  
#mse253
#module5 