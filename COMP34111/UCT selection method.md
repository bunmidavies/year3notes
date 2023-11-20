[[COMP34111]]

- UCT is an exploring strategy, similar to [[epsilon greedy selection]] 

- each node $v$ stores two quantities:
	1. $Q(v)$ - the sum of all payoffs received (all playouts which pass through $v$)
	2. $N(v)$ - the number of times node $v$ has been visited 
- at the parent node $v$, UCT selects the child $v'$ which maximises:
$$\frac{Q(v')}{N(v')} + C \sqrt{\frac{2\ln N(v)}{N(v')}}$$
#### algorithm
1. select next node to be evaluated (using selection method)
2. evaluate all children once
3. repeatedly evaluate the child with the highest 