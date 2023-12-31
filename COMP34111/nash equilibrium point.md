[[COMP34111]]
[wikipedia](https://en.wikipedia.org/wiki/Nash_equilibrium)

> [!example] idea
> - if every player is looking to play the best move in response to the strategies of the other players ([[best response]]), then there is a point where every player reaches the best response to the other players best response


- this means that every player cannot change their strategy without their payoff decreasing, so in short every player simultaneously has the best response to each other
- this can be written as $(s^*_1,s^*_2,...,s^*_l)$, where
	- each $s^*_i$ is a strategy for player $i$
	- each strategy is the best response to all other strategies:
$$p_i(s^*_1,...,s^*_{i-1},s^*_i,s^*_{i+1},...s^*_i) \geq p_i(s^*_1,...,s^*_{i-1},s_i,s^*_{i+1},...s^*_i)$$
- for games represented by tables, you can figure out which corresponding strategies are nash equilibriums by finding a cell where neither play can change ==only their move== in order to increase their payoff

![](https://i.imgur.com/5iC9Bp9.png)
- note the point about ==perfect information== is important, since 2 person zero sum games of imperfect information (e.g. rock paper scissors) can have no equilibrium points