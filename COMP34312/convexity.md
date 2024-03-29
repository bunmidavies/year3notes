[[COMP34312]]

- convex functions can be informally described as one whose graph between any two points $x$ and $y$ always lie below the straight line joining the points $(x,F(x))$ and $(y, F(y))$
- ==the function essentially 'hangs downwards' between any two points==

# undifferentiable functions
- the formal definition for undifferentiable functions is as follows: 

A function, $F: \mathbb{R}^p\rightarrow\mathbb{R}$ will be said to be. aconvex function if $\forall x,y \in \mathbb{R}^p$ and $\forall \theta \in [0,1]$ we have:
$$F(\theta x + (1 - \theta)y) \leq \theta F(x) + (1 - \theta) F(y)$$

# differentiable functions
- an at least once differentiable function $F: \mathbb{R}^p\rightarrow\mathbb{R}$ is convex if, $\forall x,y$ we have:
$$F(x) + \nabla F(x)^T (y-x) \leq F(y)$$