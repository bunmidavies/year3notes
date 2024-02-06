[[COMP34312]]

- population risk represents the hypothetical ==true== risk, using all possible data we may ever encounter (the entire population)
- we can then think of a population risk minimizer in a similar manner to [[empirical risk minimization|empirical risk minimizer]]

- our optimal model over ==all possible functions==, minimizing population risk for squared loss, can be denoted as $y*$
$$y* := \textrm{arg}\textrm{inf}_{f\in\Omega}R(f)$$
- empirical risk is always an ==estimate== of population risk

- between the empirical risk minimizer and the population risk minimizer, the difference in risk is known as [[excess risk]]