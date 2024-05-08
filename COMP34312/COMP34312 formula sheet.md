[[COMP34312]]

# Generalisation Bounds

- the probability of a single model violating tolerance bound $\epsilon$ - that is, the difference between the empirical risk and population risk $\geq \epsilon$
$$p(|\hat{R}(f,\mathcal{S}_n) - R(f)| \geq \epsilon) \leq \delta = 2\exp(-n\epsilon^2)$$

- extending this to a finite function class $\mathcal{F}$ thus containing $|\mathcal{F}|$ models, we can define $\delta$ as being the bound on the probability of ==at least one model== in $\mathcal{F}$ violating tolerance bound $\epsilon$

$$p(\exists f \in \mathcal F , |\hat{R}(f,\mathcal S_n) - R(f)| \geq \epsilon) \leq \delta = 2|\mathcal{F}|\exp(-2n\epsilon^2)$$
- using $\delta$, we can then put a bound on population risk using empirical risk

$$R(f) \leq \hat{R}(f,\mathcal S_n ) + \sqrt{\frac{\ln (|\mathcal F|) + \ln (1/\delta)}{2n}}$$
*true error = training error + term dependent on training samples and function capacity*

# Bias-Variance Decomposition

