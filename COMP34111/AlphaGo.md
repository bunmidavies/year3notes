[[COMP34111]]

- AlphaGo (created by Deepmind team) combines supervised learning, reinforcement learning and [[monte carlo tree search]]
- alphago is based on a variant of MCTS - "Asynchronous policy and value MCTS"
	- the value of the newly added node $s$ is a linear combination of the output of a value network, and the result of roll-outs (layouts),
		$$V(s) = (1-\eta)V(s|W) + \eta Q(s)$$
	- standard MCTS only uses the roll-outs - $\eta$ is an adjustable learning parameter
- alphago starts with a strong player, using a learned selection strategy from professional games - this requires a lot of data, using a lot of computational resources
#### main components of AlphaGo
1. Supervised learning policy network: a deep CNN which learns to replicate expert players using supervised learning
2. Policy learning network: an identical reinforcement learning neural network, initialised to the supervised learning policy network, but uses reinforcement learning and self-play using ==policy gradient== reinforcement learning
3. Value network: Learns the value of board positions for both players from the policy network
4. Roll-out network: A simple linear policy network which decides moves during roll-outs