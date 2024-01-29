[[COMP34111]]

There are 3 main properties which make up a good heuristic
### Admissible
- The heuristic always underestimates the true distance
- In a state space, a heuristic is considered admissible if for all nodes $x$, it is no longer than the true shortest distance to the goal $t$
- If a heuristic is admissible, this implies that when the goal is popped from the priority queue, the shortest path to the goal has been found

### Monotonic
- Monotonicity can also be known as consistency - a triangle inequality is satisfied
- it implies that the heuristic to any node $x$ will be less than or equal to the heuristic of node $y$ + the cost from $y$ to $x$

### Informative
- the closer the heuristic function is to the true distance, the more informative a heuristic is
- for instance, the most informative heuristic will return the true shortest distance for any node - meanwhile, the least informative heuristic will return 0 for all nodes
- with the notion above you can imply that heuristic $h'$ is more informative than heuristic $h$ given:
	- $h'(x) \geq h(x)$ for all nodes $x$