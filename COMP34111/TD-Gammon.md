[[COMP34111]]

- initially built around 1994, TD-Gammon is a 'very good' backgammon playing program which produces a board evaluation function $V(s)$ (i.e. uses stte value learning) - combined with [[TD-Lambda Learning]] principles, and two main components
	1. Predictor Network: multi-layer perceptron, predicting game outcomes from the current board position
	2. Controller: generator of all legal moves from current position, which can then be used by predictor network to determine the best move to take

- emphasis is put on the controller being necessary, since there is no point to be seen in wasting time learning moves that aren't legal - self-play with the network beginning from a random state (i.e. 0 game knowledge)
- the first versions of TD-Gammon were already significantly good at the game, able to win regional tournaments, then version 2.1 of TD-Gammon essentially became what was considered the best player in the world - new strategies which were adopted by humans were discovered by TD-Gammon