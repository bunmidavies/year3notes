[[COMP34111]]

- $TD(\lambda)$ is a sped up version of [[tabular Q-learning]] using a heuristic
- when a reward is received, credit/blame is assigned to the action
	1. the previous action receives a value with a weight of 1
	2. the action before that receives a value with weight $\lambda \times \gamma$
	3. the action before that receives a value with weight $(\lambda \times \gamma)^2$
	4. etc...
- where $\lambda$ is a parameter between 0 and 1

- this differs to Q-learning since it doesn't only update the state which immediately led to a reward, but it works its way backwards to update every state in the sequence which led to the reward

- a famous application of TD-learning is TD-Gammon 