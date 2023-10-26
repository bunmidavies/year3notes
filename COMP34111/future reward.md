[[COMP34111]]

- the future reward within reinforcement learning is the sum of all rewards from now until the end of the game
$$r_1 + r_{t+1} + r_{t+2} + ... = \sum^{\textrm{end}}_{t'=1}r_{t'}$$

- ==discounted future reward==: the longer you wait, the less valued the reward by a factor $\gamma$ between 0 and 1 - essentially rewards are worth less the longer you wait for them
- in the context of states and actions, this means future rewards become $\gamma$ raised to the number of steps required to achieve the reward, *assuming optimal steps are taken going forward*
- discounting ensures shorter paths - the longer the path you take, the more likely you are to make errors

### learning the future reward
- the value of a non-terminal node will be the expected future reward, discounted by how long it takes to get it