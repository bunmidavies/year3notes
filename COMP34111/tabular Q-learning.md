[[COMP34111]]

- the Q-table predicts the immediate reward + the expected (discounted) reward assuming the best actions are taken from that state onwards:
- $Q(s_t,a_t) =$ immediate reward + estimate of future rewards
$$r_t + \gamma\max_{a'}Q(s_{t+1},a')$$

- the general algorithm is as follows:
1. observe current state $s_t$
2. choose action using policy derived from $Q$:
	   - exploiting = $a_t = \textrm{argmax}_{a'}Q(s_t,a')$
	   - exploring = $a_t = \textrm{random action}$
3. observe new state $s_{t+1}$ and any reward $r_t$
4. update $Q$ as such:
$$Q(s_t,a_t)\leftarrow Q(s_t,a_t) + \alpha [r_t + \gamma\max_{a'}Q(s_{t+1},a') - Q(s_t,a_t)]$$
- this basically means:
$Q(s_t,a_t)\leftarrow Q(s_t,a_t) + \alpha$ [current reward + predicted discounted future reward]


- each cell within the table - $Q(s,a)$ - will eventually converge to:
	- the expected future reward one gets taking an action $a$ from $s$
	- discounted by the time taken to get it, assuming the best action is picked from that point onwards

- tabular Q-learning is proven to converge to the correct answer if every state is visited, and every action is used an infinite number of times (i.e. via learning)