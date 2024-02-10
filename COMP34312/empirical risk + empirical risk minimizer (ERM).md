[[COMP34312]]

- empirical = experimental, using an actual training set
- ==empirical risk refers to the error of a sample==, $\mathcal{S}_n = \{(x_i,y_i),i=1,...,n\}$ denoted with $\hat{R}$

$$\hat{R}(f,\mathcal{S}_n) := \frac{1}{n}\sum^n_{i=1}\ell(y_i,f(x_i))$$

- the ==empirical risk minimizer (ERM)== is a sort of hypothetical idea where we search across all possible models we have ($\mathcal{F}$), to find the minimum empirical risk i.e. given we have some training sample and family of models, we find the model within that family which has the lowest training error

$$f_{erm} := \textrm{arginf}\hat{R}(f,S_n)$$
