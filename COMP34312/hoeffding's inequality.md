[[COMP34312]]


- this only holds for a fixed function/model, $f$ - i.e. a particular configuration of some type of ML model
- ideally, we would want this to hold for <u>all</u> functions within our model family, $\mathcal{F}$ (assuming we have a finite function class)
- we do this through adjusting our probability to being *there exists at least **one** model within our model family* violating our tolerance bound $\epsilon$

- we end up with the following generalisation bound, with probability $1 - \delta$
$$R(f) \leq \hat{R}(f,\mathcal{S}_n) + \sqrt{\frac{\ln (|\mathcal{F}| + \ln (1/\delta))}{2n}}$$

population risk $\leq$ empirical risk + tolerance bound ($\epsilon$)