[[COMP34111]]

- the most basic exploration-exploitation search strategy, but often the default approach since it's reasonably effective

$$\textrm{selected action = }\begin{cases}\textrm{current best action} & p=1-\epsilon\\ \textrm{random action} & p = \epsilon\end{cases}$$
- where $\epsilon$ is a small number between 0 and 1 - this is always initially chosen, and there isn't really a systematic method to pick this
- ==the higher epsilon is, the more exploration (random moves) takes place==

- it's often beneficial to start with a lot of exploration, then decrease the exploration over time, thus increasing exploitation (high $\epsilon \rightarrow$ low $\epsilon$), one way to do this is:
	- $\epsilon_t = \epsilon_0 / t$
	- $t = t+1$
- in this method, you'll explore all the time in the first iteration, then half a time, then a third of the time, etc

- another method:
	- $\epsilon_t = \min(T/t, 1)$
	- $t = t + 1$
- $T$ = number of explore-only iterations - once $t > T$, exploration will begin to reduce

- ==note that if the environment/rewards are changing over time, epsilon should be fixed== 

