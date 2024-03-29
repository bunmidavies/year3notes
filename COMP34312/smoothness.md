[[COMP34312]]

- smoothness, also referred to as ==lipschitz-smoothness==, is very similar to regular [[lipschitzness]], except the gradients of functions are used

- a function $F : \mathbb{R}^p\rightarrow\mathbb{R}$ is said to be $\beta-$smooth or $\beta-$lipschitz smooth or $\beta-$gradient lipschitz if its gradients are $\beta-$lipschitz i.e. 
- $\forall x,y,$ we have:
$$|| \nabla F(x) - \nabla F(y) || \leq \beta||x-y||$$

- for instance, $F(x)=x^2$ is smooth with $\beta = 2$
- ==the definition of 'smoothness' in ML differs to the typical definition of 'smoothness' in calculus - functions which are infinitely differentiable==