[[COMP34312]]

- ==approximation error== - the error between the the best possible model we can create in our family $f*$ (NOT the erm) and [[bayes model]] $y*$ - this is due to having a restricted model family, and since we choose the model family the error is a constant
$$R(f*) - R(y*)$$

- ==estimation error== - the error between the [[empirical risk + empirical risk minimizer (ERM)|erm]] and Bayes model, due to having a limited sample - the bigger the sample, the (most likely) closer the ERM would be to $f*$ - but obviously this depends on the sample $\mathcal{S}_n$, thus is a random variable
$$R(f_{erm}) - R(f*))$$

# overfitting/underfitting tradeoff

- as we increase the size of our model family - denoted $|\mathcal{F}|$ - approximation error is likely to decrease (potentially to 0 if we manage to encapsulate $y*$ within $\mathcal{F}$), but the estimation error increases, as the space becomes larger so it becomes harder to find $f*$ by chance (remember that estimation error is a random variable) 
- ==overfitting== tends to occur when our function class is too ==large==, relative to the amount of data we have
- meanwhile ==underfitting== occurs when our function class is too ==small==, relative to the data we have

# approximation/estimation/optimisation decomposition

- previous notes assume that we can find the ERM, but as also mentioned, the process to find the ERM doesn't really exist - therefore, we have one more type of risk, one between our current model and the ERM
- ==optimisation error== is the component of the [[excess risk]] caused by a poor learning algorithm

- therefore, the excess risk of a sub-optimal model $f$ within some sample space $\mathcal{S}_n$ can be expressed as

$$\underbrace{R(f)-R(y*)}_{\textrm{excess risk of f}}=\underbrace{R(f)-R(f_{erm})}_{\textrm{optimisation error}} + \underbrace{R(f_{erm})-R(f*)}_{\textrm{estimation error}} + \underbrace{R(f*)-R(y*)}_{\textrm{approximation error}}$$


- in short
	- optimisation error = faults in learning algorithm
	- estimation error = faults in the data
	- approximation error = faults in the selected model family

- the [[excess risk]]