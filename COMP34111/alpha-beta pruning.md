[[COMP34111]]

The first thing to understand is that alpha beta pruning can be added to the already existing minimax algorithm, and ==does not change the outcome== of the algorithm. It simply exists to speed up the process, and skip nodes which will not affect the outcome of the algorithm

How alpha beta pruning actually works can be seen as moving on from a node as soon as it's known that no further nodes will affect the algorithms result. This works through:

==at a maximising node==, $\beta$ comes from the parent, and $\alpha$ is the highest-value child so far

==at a minimising node==, $\alpha$ comes from the parent, and $\beta$ is the lowest-value child so far

==**when to stop processing**==
for alpha-beta pruning, you stop processing the current node once $\alpha \geq \beta$

within minimax, we always assume the opposing player plays their best strategy - this is quite a key point to understanding how alpha-beta pruning works

you have alpha and beta, which establish an interval of payoffs that you are interested in - this begins as $(-\infty,\infty)$ - the idea is that you use the values from subgames to determine whether other subgames need to be traversed

- for a minimising node, whatever minimum value you end up with is the ==maximum== that the parent node can achieve given it picks that node - we know this because minimax is attempting to find the ==best payoff in the worst case==
- for a maximising node, whatever maximum value you end up with becomes the ==minimum== value the parent node can achieve given it plays into that maximising node
- using this logic, it is possible to establish a range within each node/subgame as it traverses subnodes/subgames - 

- example 1: maximising node currently with $[-10,10]$ child has value of $-20$ - this node can be ignored since there are better worst case scenarios the maximising node can take
- example 2: maximising node currently with $[-10,10]$ child has value $20$ - ignore this child and return it to the parent. This is since the minimising player already has a guaranteed 10 at worst, so it would never choose this option if it already has a better strategy (?)