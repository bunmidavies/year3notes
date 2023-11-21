[[COMP34111]]

- in monte carlo tree search, a game tree is built incrementally, but ==asymmetrically==
- for each iteration, a tree policy is used to find the most urgent node to expand, using a strategy which balances exploration and exploitation
- this urgent node then has a playout run from it i.e. typically random moves played to the end - according to the reward, the MCTS tree is updated accordingly (from the end game node back up to the original node where the playout started)
- MCTS can be split up into 4 main phases, which each build on each other and require the 'output' of the previous stage in order to continue

***

# selection
- the current MCTS tree is traversed from the root to a leaf, using some selection rule - the most common rule is the [[UCT selection method]] 
- once you reach what your selection method deems to be the most important node (which isn't terminal), it can be expanded 
- the selection method is also known as the ==tree policy==
# expansion
- after some selection algorithm has been applied to the existing MCTS tree, an unvisited child of the previously selected node is added to the MCTS tree. In some other cases, all children of the leaf within the MCTS tree may be added
# rollouts
- a playout/simulation/rollout is run from the newly added node using a chosen policy until the end of the game is reached - typically, this might just be any random move possible, but some approaches also have a small database of heuristics to make suitable moves 
- these rollouts require ==self-play== since the opponent cannot actually respond to these moves being made
- whatever methodology is being used is typically called the ==default policy== 
# backpropagation/backup
- the reward received from the previous playout essentially makes its way back from the terminal node, up to the original node where the playout began
- each node has its visit count incremented, and depending on whether the playout resulted in a win or not, the win count 

***

- essentially, as the game goes on you're building up an MCTS tree and repeatedly running/playing out scenarios of the game to determine what your next best move is
- with these in place, the general approach using MCTS to find the next move is
```
v0 = current board position
while (time remaining):
	expansionNode = expand(selectionMethod(v0))
	reward, terminalNode = 	rollout(expansionNode)
	backpropagate(expansionNode, terminalNode, reward)

return BestChild(v0)
```
- `BestChild` is another implementation decision

# selecting a final move
- a final move must be selected once the MCTS for the current move ends, i.e. when time runs out - the final move must be a child of the current board position (i.e. the current root)
- a number of different methods exist:
	- ==max child== - the child with the highest average reward
	- ==robust child== - the child with the highest visit counter
	- ==max-robust child== - the child with the max visits and average reward (if this doesn't exist, the search must continue until one does exist)
	- ==secure child== - the child which maximises a lower confidence interval