[[COMP34312]]

$$\hat{R}(f,\mathcal{S}_n) \rightarrow R(f)$$
as $n \rightarrow \infty$

- empirical risk "converges in probability" to the population risk
- this law says nothing about the ==rate== at which empirical risk converges to population risk

# example

assume $x = \{0,1\}$ is a random variable following distribution $p(x)$

the expected (true) value is:
$$\mathbb{E}[X] = (0\times p(x=0)) + (1\times p(x=1))$$
where $X$ represents the loss of the model over the population (if that were possible)

our estimate (empirical) is:
$$\frac{1}{n}\sum_{i=1}^nx_i$$

abs. value of difference i.e. deviation = $|\mathbb{E}[X] - \frac{1}{n}\sum_{i=1}^nx_i|$

consider we find the probability of this deviation being greater than some small *tolerance bound*, $\epsilon$

$p(|\mathbb{E}[X] - \frac{1}{n}\sum_{i=1}^nx_i| \geq \epsilon)$

if we were to graph the deviations we get and their probabilities, we can find the probability of this deviation being greater than $\epsilon$ as the area beneath the graph

![](https://i.imgur.com/XIaU4jC.png)

we can say this probability is at most, $\delta$

$$p(|\mathbb{E}[X] - \frac{1}{n}\sum_{i=1}^nx_i| \geq \epsilon) \leq \delta$$

regardless of the characteristics of the model, data, etc, $\delta$ can be computed
$$\delta = 2\exp (-2n\epsilon^2)$$
- $n$ = number of samples
- $\epsilon$ = our tolerance bound
- essentially, the probability of our empirical risk using $n$ samples deviating so far ($\epsilon$ far) from the population risk is bounded by $\delta$
- this is also known as [[hoeffding's inequality]]

- relating this to the concepts of [[population risk]] and [[empirical risk + empirical risk minimizer (ERM)|empirical risk]], we can write this as:

$$p(|R(f) - \hat{R}(f,\mathcal{S}_n)|\geq \epsilon) \leq \delta (= 2\exp (-2n\epsilon^2))$$