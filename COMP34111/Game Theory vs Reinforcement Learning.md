[[COMP34111]]
[stackexchange](https://stats.stackexchange.com/questions/208661/whats-the-relation-between-game-theory-and-reinforcement-learning)

- there are specific situations in which learning is preferred to minimax:
	- good heuristics cannot be found
	- branching factor is very high
	- equilibria being hard to compute (games of incomplete info, general sum games, games with many players) 

- ==common example: Go==: the branching factor is high (played on a 19x19 board), it has a deep game tree, and lacks any known reliable heuristic value function for non terminal board positions
- parallel terms between the two fields are shown below

| Game theory | Reinforcement learning |
| ----- | ----- |
| Strategy | Policy |
| Payoff | Reward |
| Node (board position) | State |
| Heuristic (evaluation) | Function approximation |