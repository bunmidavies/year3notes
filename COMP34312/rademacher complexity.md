[[COMP34312]]

# Rademacher complexity

For a function class $\mathcal{H}$, suppose being given an $n$-sized data-set $\mathcal{S}_n$ of points $z_i$, in the domain of elements in $\mathcal{H}$. Let $\epsilon$ be a $n$-dimensional random vector s.t. its coordinates are sampled as $\epsilon_i \approx \pm 1$ 

The ability of the function class to model noise, and this idea is related to whether we can ==learn==

# average Rademacher complexity

- the equation provides a bound on the expectation (over training data) of the worst generalization error among all possible predictors
- therefore, this upper bound is dependent on:
	- loss
	- predictor class
	- distribution
	- number of samples

# sample complexity

- it is possible to calculate estimates of the number of samples needed to attain a target accuracy of learning, using the idea of Rademacher complexity
- as the function class $\mathcal{H}$ gets more and more complicated, sample complexity estimates begin to become wild overestimations of the actual number of samples required
- this gap is at the cutting edge of machine learning research