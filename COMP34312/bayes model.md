[[COMP34312]]

- the Bayes model is another hypothetical model, but this time with no restriction on the model family $\mathcal{F}$
- essentially, we find the model across all pososible models $\Omega$ with the minimum [[population risk]]
$$y* := \textrm{arg}\textrm{inf}_{f\in\Omega}R(f)$$

- for ==squared loss==, $y* = \mathbb{E}_{y|x}[x]$ and for 0/1 loss, $y* = \textrm{argmax}_yp(y|x)$
- again, it should be remembered that this model as well as the population risk minimizer aren't computable in real scenarios since we'd require the full data distribution