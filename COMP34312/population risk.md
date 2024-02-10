[[COMP34312]]

- population risk represents the hypothetical ==true== risk, using all possible data we may ever encounter (the entire population)
- in terms of averages/expected values, it can be expressed as
$$R(f ) ∶= \mathbb{E}_{(x,y)∼D} [ℓ(y, f (x))] = ∫ ∫ ℓ(y, f (x))p(x, y)dxdy$$
- $\mathbb{E}_{(x,y)∼D}$ denotes 'expectation with respect to the true data distribution' - i.e. the average over all possible inputs (if that were possible)
- population risk is also known as the ==generalisation error==

- we can then think of a population risk minimizer in a similar manner to [[empirical risk + empirical risk minimizer (ERM)|empirical risk minimizer]] - the model in our model family $\mathcal{F}$ which returns the lowest population risk
$$f* := \textrm{arginf}_{f\in \mathcal{F}} R(f)$$

- empirical risk is always an ==estimate== of population risk

- between the empirical risk minimizer and the population risk minimizer, the difference in risk is known as [[excess risk]]