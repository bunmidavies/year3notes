[[COMP34212]]

- there are two main aspects of trust in human-robot interaction: the trust between the robot and humans, and vice-versa
- to enable trust, a  theory of mind, also known as perspective taking, is developed — "that is, the ability to infer the cognitive states of other agents (i.e. humans) with which it is interacting, predicting their behaviour, and acting appropriately"
- bayesian models are typically used for belief and theory of mind

# development of ToM

- as mentioned, separate bayesian networks can be made per speaker/interaction - actions are made based on a consequence of internal belief, and an informants action
- essentially, MLE is used with information to track the reliability of who is being interacted with, in order to set the beliefs within the network - over a number of interactions with different agents, different amounts of belief can be assigned to different agents
- Sally-Anne test:
![500](https://i.imgur.com/LJfjzTX.png)
- no 3-4 year old children understand that sally doesn't know

# can i trust my robot?

- there are a number of anthropomorphic and social factors which decide whether a human trusts a robot:
	- social gaze
	- speech
	- anthropomorphic priming
	- share actions
	- imitation
- experiments within lecture show:
	- social gaze is only important for humanoid robots (produces more trust)
	- after interacting with non-humanoid robots first, trust diminishes even if interacting with humanoid robot afterwards
	- "nasty" investment robot with non-joint attention is trusted less over time, while whether a "nice" investment robot is joint or not doesn't affect trust