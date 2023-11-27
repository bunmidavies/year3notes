[[COMP34111]]

- reinforcement learning agents essentially explore different actions/sequences of actions to find which of these should be exploited - essentially, an effective policy is learned through trial and error, without a teacher

- there are 3 key concepts within RL:
	1. ==exploration-exploitation tradeoff==: exploration is finding new states and actions which may lead to higher rewards, while exploitation is using previously discovered knowledge to gain rewards - the most common strategy employing both is the [[epsilon-greedy policy]]
	2. learning to take actions based off future payoffs
	3. [[learning through self play]]

- there is a concept of time within reinforcement learning, which is just represented as $t$ - the reward, state, and action taken at time $t$ can be represented by $r_t$, $s_t$ and $a_t$ 

- the method which an agent uses in order to choose some action in the state at time $t$ i.e. $s_t$, is known as the policy - $\pi(A_t|s_t)$ - this is a conditional probability of making some action given the agent is in state $s_t$
- once learning is complete, this policy can become deterministic
- the overall goal of reinforcement learning is to find $\pi*$ - the optimal policy, where for every possible action/state pair, the reward has been optimised

- ==the reward function is unknown== - this is an important point since if the reward function were known, then we would be dealing with a Markov Decision Problem (MDP) - trial and error is necessary since we don't know the reward function