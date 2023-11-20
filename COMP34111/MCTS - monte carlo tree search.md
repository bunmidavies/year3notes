[[COMP34111]]

- in monte carlo tree search, a game tree is built incrementally, but ==asymmetrically==
- for each iteration, a tree policy is used to find the most urgent node to expand, using a strategy which balances exploration and exploitation
# selection
- the current MCTS tree is traversed from the root to a leaf, using some selection rule - the most common rule is the [[UCT selection method]] 
# expansion
- after some selection algorithm has been applied to the existing MCTS tree, typically the selected child is added to the MCTS tree. In some other cases, all children of the leaf within the MCTS tree may be added
# rollouts
- a playout/simulation/rollout is run from the newly selected node using a chosen policy until the end of the game is reached - typically, this might just be any random move possible, but some approaches also have a small database of heuristics to make suitable moves - these rollouts require ==self-play== since the opponent cannot actually respond to these moves being made
# backpropagation
- the reward received from the previous playout essentially makes its way back from the terminal node, up to the original node where the playout began
- each node has its visit count incremented, and depending on whether the playout resulted in a win or not, the win count 

- while time is remaining:
	- use the tree policy of current game state to find the next node to expand
	- use the default policy to simulate from selected node