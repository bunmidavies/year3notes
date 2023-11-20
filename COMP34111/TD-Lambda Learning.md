[[COMP34111]]

- $TD(\lambda)$ is not used as much anymore, but is an approach which can be taken to speed up state-value/V learning and [[tabular Q-learning]] 
- in both V/Q learning, you may typically initialise all rewards in all states/state-action pairs to be 0. This means that until you reach an immediate reward, nothing will be updated, since its all essentially 0-0
- once you reach an immediate reward, the move just before is updated, and the move before that will eventually be updated (given the same sequence is taken), and this reward will move further back over time - ==this backward movement can be slow==

- when a reward is received, credit/blame is assigned to the action
	1. the immediately previous action receives a value with a weight of 1, as normal - they'll just receive the regular $(\alpha \times r)$ reward
	2. the action before that receives a value with weight $(\lambda \times \gamma)$
	3. the action before that receives a value with weight $(\lambda \times \gamma)^2$
	4. etc...
- $\lambda$ is a chosen parameter between 0 and 1

- by not only updating the state which immediately led to a reward, but working your way backwards to update every state in the sequence which led to the reward, you can significantly increase the speed of learning
- a typical way to implement this is through just keeping track of what plays were made for the current episode

- a famous application of TD-learning is [[TD-Gammon]] 