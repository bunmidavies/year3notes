[[COMP34111]]

- the Q-table predicts the immediate reward + the expected (discounted) reward assuming the best actions are taken from that state onwards:
- $Q(s_t,a_t) =$ immediate reward + estimate of future rewards
$$r_t + \gamma\max_{a'}Q(s_{t+1},a')$$

- each cell within the table - $Q(s,a)$ - will eventually converge to:
	- the expected future reward one gets taking an action $a$ from $s$
	- discounted by the time taken to get it, assuming the best action is picked from that point onwards

- tabular Q-learning is proven to converge to the correct answer if every state is visited, and every action is used an infinite number of times (i.e. via learning)