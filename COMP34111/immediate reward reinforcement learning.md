[[COMP34111]]

1. at time $t$ the agent (game player) is in state $s_t$
2. the agent chooses and takes an action $a_t$ from a set of actions possible at that time $a_t \in A_{s_t}$
3. the agent then receives a reward $r_t$

- there are 3 main aims to this
	1. learn the expected reward for every action taken from every state
	2. use the expected reward to find the action from every state which maximises the expected reward (through ==exploring== and ==exploiting==)
### tabular approach
- the tabular approach involves maintaining a table $Q(s,a)$, where the table stores the current estimate of the expected reward for taking an action $a$ from state $s$

- the learning algorithm is as follows, using a learning rate $\alpha$ between 0 and 1
	1. select $\epsilon$ value
	2. initialise $Q(s,a)$ for all $s$ and $a$; $s_1 \leftarrow$ start state, $t \leftarrow 1$
	3. repeat the following until no time is remaining:
		3.1. observe state $s_t$
		3.2. using $\epsilon$, choose either the best action according to the current $Q(s_t,a)$ or a random action
		3.3. observe the reward ($r_t$)
		3.4 update $Q(s_t,a_t)$ where $a_t$ was the action taken from $s_t$
		$Q(s_t,a_t) \leftarrow Q(s_t,a_t) + \alpha[r_t - Q(s_t, a_t)]$
		3.5. $t \leftarrow t + 1$

- once a model has been trained i.e. the table has been updated, a greedy policy to use the table is to always pick the action which produces the highest expected reward