[[COMP34111]]

- monte carlo board evaluation allows you to generate a simple heuristic function for games, through essentially mindlessly playing the game repeatedly
- ==playouts/rollouts/simulations== = players making random moves until the end of the game is reached
- in order to evaluate any board position, the following happens:
	- play the game to the end from that board position, with all players choosing random moves every time, and record the payoff each time
	- return the average payoff
- therefore we are estimating the strength of the current board position from the average payoff of the nodes accesible to it

- the main downside of this is the number of playouts you'd need for a useful function - despite not playing against a player who is going to make random moves every time, the evaluation can still prove useful