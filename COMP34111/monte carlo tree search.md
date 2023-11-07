[[COMP34111]]



- in monte carlo tree search, a game tree is built incrementally, but ==asymmetrically==
- for each iteraiton, a tree policy is used to find the most urgent mode to expand, using a strategy which balances exploration and exploitation
- a simulation is run from the selected node using a default policy (i.e. random choice)

- while time is remaining:
	- use the tree policy of current game state to find the next node to expand
	- use the default policy to simulate from selected node